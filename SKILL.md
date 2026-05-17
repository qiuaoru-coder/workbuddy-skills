---
name: ttcx4-lottery
description: >-
  This skill should be used when the user asks for ttcx4 daily numbers,
  says "告诉我今天的10个号码", "更新彩票并给号码", or wants the full
  lottery workflow run end-to-end. It fetches the latest Eastmoney history,
  updates the master Excel, recalculates the analysis Excel, and returns 10
  recommended 4-digit number sets in the agent conversation.
---

# ttcx4-lottery

## Overview

执行一个固定闭环：抓取东方财富天天彩选4历史开奖、刷新主 Excel、重算分析 Excel，并在 agent 对话框里输出默认 10 组号码。

## When To Use

在这些场景触发本 skill：
- 用户说“告诉我今天的10个号码”
- 用户说“更新彩票并给号码”
- 用户提到“天天彩选4”、“ttcx4”、“彩选4分析”
- 用户希望把最新开奖号写回 Excel 并立刻得到下一期的 10 组号码
- 用户第一次使用该流程，目标目录里还没有任何历史 Excel 文件

## Workflow

### 1. 识别数据目录

优先把当前工作区根目录当作数据目录，并在该目录中读写这两个文件：
- `ttcx4_历史开奖号码.xlsx`
- `ttcx4_位置数字偏差分析.xlsx`

如果用户明确给了别的目录，就使用那个目录。

### 2. 选择 Python 解释器

按以下顺序选择解释器：
1. `<data-dir>/.venv/bin/python`
2. `python3`

如果缺少 `openpyxl` 或 `scipy`，先安装后再执行脚本。

### 3. 运行闭环脚本

运行：

```bash
"<python>" "$HOME/.workbuddy/skills/ttcx4-lottery/scripts/ttcx4_pipeline.py" --data-dir "<data-dir>"
```

默认行为：
- 自动识别东方财富历史页总页数
- 从 `page=1..N` 全量抓取，其中 `N` 为自动识别到的总页数
- 即使目标目录里还没有 Excel，也会从零首次生成两个结果文件
- 每次执行都按最新历史页数重新全量构建结果，而不是依赖旧 Excel 做增量补丁

如遇网页结构变化导致自动识别页数失败，可临时手动指定页数：

```bash
"<python>" "$HOME/.workbuddy/skills/ttcx4-lottery/scripts/ttcx4_pipeline.py" --data-dir "<data-dir>" --pages "<N>"
```

脚本会自动：
1. 识别总页数并抓取全部历史页
2. 重建并覆盖主 Excel
3. 重算位置频数、偏离率、卡方检验、偏多偏少、明日10组
4. 做抓取完整性校验（页数齐全、非末页记录数一致、无重复期号）
5. 输出 JSON 摘要，供 agent 提取并在对话框回复用户

### 4. 读取脚本输出并回复用户

从脚本输出里提取：
- 总页数
- 最新一期
- 最新开奖号码
- 总样本数
- 统计结论
- 抓取校验结果
- 10 组号码

默认用中文回复，先给 10 组号码，再补几行数据更新结果，例如：
- 已同步到最新期开奖：2026107 / 6379
- 当前历史页数：105
- 当前样本数：5229
- 抓取校验：通过（页数齐全、无重复期号）
- 位置偏差结论：基本均匀，无明显偏差

### 5. 文件交付

如果脚本更新了 Excel，交付这两个文件：
- `ttcx4_位置数字偏差分析.xlsx`
- `ttcx4_历史开奖号码.xlsx`

优先打开分析文件给用户查看，因为其中包含“明日10组”工作表。

## Notes

- 默认输出 10 组号码，不主动压缩成 5 组，除非用户再要求。
- 这是基于“近期回避 / 均值回归 + 多窗口共识 + 分散约束”的娱乐性筛选，不要把它描述成确定性预测。
- 如果东方财富页面结构变化导致抓取失败，先向用户明确报错原因，再说明需要调整解析逻辑。
- 如果抓取校验出现异常，不要把不完整的数据静默交付给用户；应先明确说明哪一类校验失败。

# GMT Review Output Guide

Use this guide when producing a formal GMT review.

## Recommended Structure

### 1. Executive Judgment

State whether the proposal is GMT-clear, partially clear, or unclear. Summarize the most important risk in 2-4 sentences.

Avoid a binary "satisfies GMT theory" unless the user explicitly asks for pass/fail. Prefer:

- "GMT chain is coherent"
- "GMT chain is partially coherent but under-specified"
- "GMT chain is currently broken at M/T support"
- "The proposal is promising but its experience GMT is unproven"

### 2. Goal Separation

Use a table:

| Type | Stated or inferred goal | Evidence in proposal | Confidence | Notes |
| --- | --- | --- | --- | --- |
| Player goal | ... | ... | High/Medium/Low | ... |
| Experience goal | ... | ... | High/Medium/Low | ... |
| Design goal | ... | ... | High/Medium/Low | ... |

### 3. GMT Map

Use one table for player GMT and one for experience GMT.

| Goal | Means | Tools | Support strength | Risk |
| --- | --- | --- | --- | --- |
| ... | ... | ... | Strong/Medium/Weak/Missing | ... |

When the design goal materially affects player or experience GMT, add a design-goal relation table:

| Design goal | Relation to player GMT | Relation to experience GMT | Risk |
| --- | --- | --- | --- |

### 4. Findings

List findings by severity:

- Critical: Breaks the core goal chain or makes the intended experience unlikely.
- Major: Significant ambiguity, missing tool support, production risk, or contradictory design logic.
- Minor: Local clarity, balance, polish, or evidence gaps.
- Opportunity: Optional improvement or useful alternative.

For each finding, include:

- Observation
- Why it matters in GMT terms
- Evidence or assumption
- Recommendation

### 5. Questions Needed

Ask only questions that would change the GMT map or recommendation. Examples:

- What is the primary intended player experience?
- Which goal has priority when player mastery conflicts with emotional vulnerability?
- Is this mechanic mandatory, optional, or expressive?
- What playtest signal would prove the intended experience is working?
- What production capacity is assumed for art, animation, AI, level design, audio, or content volume?

### 6. Action Plan

Give concrete next steps:

- Rewrite goals
- Remove or downgrade orphan tools
- Add missing tools
- Prototype the weakest means
- Define player-facing feedback
- Add playtest questions
- Clarify phase transitions
- Align scope with production capacity

## Scoring Rubric

Use scores only if helpful or requested. A 1-5 scale is enough.

| Dimension | 1 | 3 | 5 |
| --- | --- | --- | --- |
| Goal clarity | Goals are mixed or absent | Some goals are clear | All key goals are separated and prioritized |
| G-M-T support | Chains are missing | Some chains are plausible | Goals, means, and tools strongly support each other |
| Player GMT | Player task is unclear or unsupported | Core loop works but has gaps | Player goal, choices, agency, balance, and phase logic are coherent |
| Experience GMT | Intended experience is asserted only | Some tools may create the experience | Multiple tools coherently and feasibly support the experience |
| Design-goal fit | Product/design aims conflict with gameplay or experience | Fit is partial | Design goals reinforce or intentionally frame the other goals |
| Feasibility | Scope or quality bar is implausible | Feasible with risks | Feasible with clear production assumptions |

## Tone

Be direct and specific. Treat the designer as a collaborator. Do not overclaim certainty about subjective experience. Distinguish "not enough information" from "design problem."

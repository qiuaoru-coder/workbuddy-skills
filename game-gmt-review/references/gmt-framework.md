# GMT Framework Reference

Use this reference to apply GMT to game design reviews.

## Three Goal Types

### Player Goal

Define the player goal as the result the player is asked to achieve inside the game situation.

Examples: defeat the final boss, survive until a ceasefire, reach the mountain top, win the match, solve a puzzle, collect enough currency, occupy a point, create an object, optimize a system.

Analyze:

- Subject: player
- Desired result: concrete in-game outcome
- Path: interaction with game rules, systems, concepts, and mechanics

Common player goal families:

- Complete: find/discover, obtain, solve, reach, occupy, create
- Win: defeat, eliminate, overwhelm
- Maintain: optimize, exist/survive/endure

### Experience Goal

Define the experience goal as the sensory, psychological, emotional, cultural, cognitive, or thematic response the designer wants players to have.

Examples: fear and curiosity, confidence from mastering a skill, sympathy, loneliness, cultural understanding, tension from competition, satisfaction from cooperation, awe from a strange world, joy from music and rhythm.

Analyze:

- Subject: designer
- Desired result: intended player experience
- Path: interaction, sensory feedback, narrative, structure, aesthetics, theme, worldbuilding, pacing, and meaning

### Design Goal

Define the design goal as the product, craft, technical, structural, or strategic effect the designer wants to achieve through specific design choices.

Examples: simpler UI, an innovative physics expression, genre innovation, long-term live operation space, a modernized Counter-Strike-like experience, a unique cooperation structure, a particular production pipeline advantage.

Analyze:

- Subject: designer
- Desired result: product/design effect or value
- Path: specific design concept, form, standard, structure, technique, technology, or method

## Goal Relationship Principles

Use these principles when checking a proposal:

- Achieving the player goal does not automatically achieve the experience goal.
- Achieving the experience goal does not automatically achieve the design goal.
- Achieving the design goal does not automatically make the player goal or experience goal work.
- Player goals, experience goals, and design goals do not need to have necessary relationships.
- Strong relation, weak relation, potential relation, and no relation can all be intentional.
- The design can start from any of the three goal types.
- A design can be interesting even if only one goal type works, but the review should name that tradeoff.
- A common failure is confusing a means or tool for a goal.

## GMT Levels

### G: Goal

Use G for the target result in the design claim. For larger games, split the overall goal into sub-goals when different means are needed.

Watch for phase changes. In session-based games, goals can change over time, and the means/tools may change with them. Review whether the new phase still feels like the same game or creates unwanted rupture.

### M: Means

Use M for high-level ways to achieve the goal. Means should be broad enough to contain multiple possible tools and hard to replace with another category.

Player GMT means often include:

- Strategy
- Tactics
- Operation or action skill
- Traversal skill
- Shooting/combat skill
- Puzzle solving or intellectual challenge
- Resource management
- Social cooperation
- Exploration
- Collection
- Creation
- Optimization
- Survival

Experience GMT means often include:

- Interaction/mechanics
- Sensory presentation
- Art, animation, audio, effects
- Narrative and worldbuilding
- Theme, culture, history, religion, philosophy, geography, region, era
- Aesthetic tone
- Structure, composition, flow, and pacing
- Genre conventions and familiar modules
- Content organization

### T: Tools

Use T for concrete executable or perceivable elements that support a means. A tool is usually close to direct player input, player perception, implementation, or production work.

Player GMT tools often include:

- 3C
- Input system
- Character abilities
- Level design
- Enemy and AI behavior
- Rules and concepts
- Prompts, UI, feedback
- Weapons, items, skills
- Economy and resource systems
- Mission objectives
- Difficulty, progression, and scoring
- Other actionable gameplay information

Experience GMT tools often include:

- World/time/space/character setting
- Story, plot, lore, dialogue, and documents
- Art style, animation, VFX, lighting
- Music, sound effects, tactile feedback
- Camera, staging, cinematic treatment
- Genre modules such as shooter, platformer, RPG, simulation, rhythm, puzzle
- Flow structure, pacing, scene sequence
- Thematic motifs and cultural materials

## Evaluating Player GMT

Review player GMT with these lenses:

- Logical relation: Do T support M, and do M support G?
- Clarity: Are G, M, and T understandable to players and designers?
- Distinctiveness: Are the choices fresh, vivid, or memorable enough for the product goal?
- System integrity: Are the support chains sufficient and necessary as a whole?
- Balance: Do the relative weights of different M and T match the goal?
- Synergy: Do M and T combine, complement, or multiply each other?
- Complexity: More M often increases depth, choice, and learning cost; more T often increases breadth, interaction variety, and agency.
- Agency elasticity: How mandatory is each M/T for reaching G, and how much freedom does the player feel?
- Phase coherence: If goals change during a session, do M/T change coherently?

## Evaluating Experience GMT

Review experience GMT with these lenses:

- Goal value: Is the intended experience valuable, fresh, market-relevant, audience-fit, or strategically necessary?
- Feasibility: Does it fit production capacity, technology, budget, timeline, and team strengths?
- Directness: Do M/T plausibly create the target feeling or meaning?
- Purity: Are M/T diluted by unrelated systems or conflicting content?
- Execution quality: Are the tools demanding enough that mediocre execution would break the goal?
- Structural integrity: Do M/T form a coherent whole, especially in mature genres with strong conventions?
- Contrast and conflict: If the design intentionally breaks convention, is the break likely to be effective?
- Evidence: Is the claim supported by examples, prototypes, playtest data, comparable games, or clear reasoning?

Experience analysis is less objectively provable than player GMT. State assumptions and uncertainty. Use user stories, prototype observations, and playtest evidence when available.

## Diagnosis Patterns

Use these patterns to name findings:

- Goal confusion: The proposal mixes player, experience, and design goals as if they were the same thing.
- Means-as-goal: The proposal names a mechanic, content type, or feature as the goal without saying what result it serves.
- Tool-as-goal: The proposal treats a concrete asset or feature as the design purpose.
- Missing means: A goal is stated but the proposal lacks high-level ways to reach it.
- Missing tools: A means is named but not implemented by concrete rules, content, feedback, or assets.
- Weak support: The tool supports the means only indirectly or too weakly.
- Orphan tool: A mechanic or asset does not support any important goal.
- Contradictory chain: A tool undermines the claimed goal or experience.
- Overloaded goal: One goal requires too many unrelated means and becomes unfocused.
- Underbuilt experience: Emotional or thematic ambition is not matched by sensory, narrative, systemic, or structural tools.
- Production mismatch: The desired experience requires execution quality, quantity, or technology beyond plausible capacity.
- Phase rupture: A later phase changes G/M/T so sharply that it becomes a different experience without clear intent.

## Review Heuristic

For every important design claim, ask:

1. Is this a player goal, experience goal, design goal, means, or tool?
2. If it is a goal, what means support it?
3. If it is a means, what tools make it real?
4. If it is a tool, what means and goal does it serve?
5. Is the relation strong, weak, absent, contradictory, or intentionally indirect?
6. What would fail first in an actual prototype or playtest?

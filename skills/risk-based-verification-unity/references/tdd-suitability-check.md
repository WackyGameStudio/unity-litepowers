# TDD Suitability Check

Use TDD automatically when all are true:

- Result is deterministic.
- Automated setup is cheap.
- Regression cost is high.

Strong examples:

- damage formula
- reward probability
- economy calculation
- level/XP curve
- inventory/equipment rule
- save/load serialization
- save migration
- data validator
- state transition rule
- input buffer priority interpretation
- seed-based procedural generation
- editor asset generator

Do not use TDD as default for visual feel, scene wiring, prefab wiring, Animator setup, physics timing feel, or package settings. Use surface evidence instead.

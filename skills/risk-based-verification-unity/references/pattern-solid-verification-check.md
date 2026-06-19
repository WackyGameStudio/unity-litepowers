# Pattern / SOLID Verification Check

Use for medium or high architecture/pattern fit risk.

## Questions

- SRP: Is responsibility split at Unity boundaries that change independently?
- OCP: Can likely variants be added without rewriting core rules?
- LSP: Can every subtype safely replace its base type?
- ISP: Are optional capabilities kept out of broad interfaces?
- DIP: Does reusable logic depend on contracts, not concrete scene sources?
- Pattern fit: Is each selected pattern justified by problem pressure?
- Pattern rejection: Are plausible rejected patterns recorded with reason?
- Lifecycle: Are Unity `Awake`, `OnEnable`, `Start`, `Update`, `OnDisable`, `OnDestroy` effects considered?
- Events: Are publisher, subscriber, naming, subscribe, unsubscribe, and debug trace clear?
- Performance patterns: Are Object Pool, Flyweight, Dirty Flag backed by measurement or clear load risk?

## Completion Evidence

Record whether implementation still matches the planned pattern decision. If implementation changed pattern or structure, update feature docs and mark main technical plan update need.

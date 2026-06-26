# Pattern / SOLID Verification Check

Use for medium or high architecture/pattern fit risk.

## Questions

1. Pressure and invariants
   - What concrete change pressure exists?
   - Which behavior invariants must remain stable?
   - Is the selected depth `routine`, `focused`, or `migration`?
2. Responsibility ownership
   - SRP: Are responsibilities split by separate reasons to change, not size?
   - Which owner has each moved state, rule, lifecycle, or feedback path?
3. Dependency direction and concrete selection
   - OCP/DIP: Can likely variants be added without rewriting core rules?
   - Is the contract consumer-owned and minimal?
   - Where is the concrete selection point?
4. LSP/ISP and composition/inheritance
   - Can every subtype or implementation safely replace its contract?
   - Are optional capabilities kept out of broad interfaces?
   - Is inheritance justified by shared invariants and lifecycle?
5. Unity lifecycle
   - Are `Awake`, `OnEnable`, `Start`, `Update`, `FixedUpdate`, `OnDisable`, and `OnDestroy` effects owned?
   - Are enable/disable, destroy, scene unload, coroutine/tween/async cleanup, and re-entry policies clear?
6. Serialized wiring and data ownership
   - Are prefab, variant, scene, serialized field, and runtime-created paths identified?
   - Is `ScriptableObject` config separate from mutable runtime state or backed by clone/reset ownership?
7. Pattern fit and rejected simpler options
   - Is each selected pattern justified by concrete pressure?
   - Are plausible simpler approaches and rejected patterns recorded with reason?
   - Are Object Pool, Flyweight, Dirty Flag, State, Strategy, Factory, Observer, Command, MVP, or MVVM backed by their failure modes and evidence needs?
8. Evidence and plan-vs-actual drift
   - Does evidence cover architecture failure modes, not only compile?
   - Does implementation still match the planned C# Architecture Profile?
   - If structure changed, were feature docs updated and main technical plan update needs marked?
9. DOTS/ECS
   - Is DOTS/ECS or Jobs/Burst justified by scale, CPU, determinism, streaming, or multiplayer pressure?
   - Are GameObject authoring/presentation and ECS runtime ownership clearly separated?

# Unity C# Refactor Playbook

Use for focused or migration C# architecture work. Routine local fixes do not need this playbook.

## 1. Preflight

- Confirm repository and Unity target identity.
- Read approved task ticket and C# Architecture Profile.
- Check Git status and protect unrelated changes.
- Confirm architecture depth, behavior invariants, changed surfaces, and evidence plan.
- If Editor-backed evidence is needed, confirm MCPForUnity target identity and console/import state.

## 2. Characterize Existing Behavior

- Capture expected current behavior before structure changes.
- Prefer existing tests or small characterization tests for deterministic logic.
- Use MCPForUnity or manual smoke for lifecycle, prefab, scene, and serialized wiring.
- Record expected and observed result, not only command names.

## 3. Introduce One Seam Without Behavior Change

- Add one contract, adapter, wrapper, composition root entry, or component boundary.
- Keep old path active until parity is observed.
- Avoid renaming serialized fields or deleting components in the same slice.
- Compile/import and read console.

## 4. Move One Responsibility

- Move one reason to change at a time.
- Keep behavior invariant visible in the slice evidence.
- Update callers through the approved selection point only.
- Stop if new public contract, asmdef direction, save/data compatibility, or architecture selection appears.

## 5. Compile/Import/Console Checkpoint

After each slice:

- refresh/import or run the relevant compile path
- read Unity console when Editor evidence matters
- run selected tests or smoke
- record changed files and observed result

Do not stack several structural changes before the first compile/import checkpoint.

## 6. Preserve Lifecycle

For lifecycle or event changes:

- keep initialization phase explicit
- keep tick phase explicit
- preserve subscribe/unsubscribe symmetry
- define re-enable behavior
- cancel coroutine/tween/async work at the owner
- verify disable/destroy/scene-unload path when relevant

## 7. Preserve Serialized Compatibility

Before removing old fields/components:

- inventory base prefabs, variants, scene instances, and runtime-created paths
- choose coexist/copy/adapter/one-shot migration path
- verify missing references, orphan components, overrides, and default values
- keep rollback until all affected assets and behavior paths are checked

## 8. Migrate Controlled Batches

Batch order:

1. base prefab or source prefab
2. prefab variants
3. scene instances and overrides
4. runtime-created objects or factories
5. tests and docs

Run evidence after each batch when behavior or wiring differs by batch.

## 9. Verify Each Slice

Map evidence to changed surfaces:

- deterministic rule: unit/EditMode test
- contract/substitution: implementation selection and caller behavior
- State: transition and re-entry evidence
- event: exact-once and unsubscribe evidence
- `ScriptableObject`: asset/config/runtime-state reset evidence
- prefab/scene: serialized references and smoke
- asmdef/API: compile and dependent caller evidence

## 10. Remove Compatibility Paths

Remove old paths only after:

- new path has equivalent behavior evidence
- affected assets are migrated
- rollback is no longer needed or is documented
- no old/new double-running path remains
- completion checker can compare planned and actual architecture

## 11. Final Evidence And Docs

- Run final evidence plan.
- Update feature `verification.md`.
- Append reusable failure/workaround learning only when log-worthy.
- Leave project-map changes for completion check.

## Stop And Replan Conditions

Return to planning instead of improvising when a slice discovers:

- unplanned public contract or asmdef direction change
- lifecycle/execution-order change outside profile
- serialized migration wider than approved affected assets
- save/load or data compatibility issue
- package, DI, service locator, or composition-root scope change
- event publisher/subscriber ownership change
- shared static or `ScriptableObject` runtime-state migration
- new affected prefab/variant/scene batch
- selected pattern no longer fits pressure
- required evidence cannot be gathered

---
description: Modify, copy, move, replace, or delete Revit elements through AEC Model Bridge.
argument-hint: [requested change]
---

Apply `$ARGUMENTS` to the live model.

1. Resolve targets by selection, IDs, category/type, parameters, or geometry, and inspect current values.
2. State affected count and intended change. For destructive or broad operations, exclude unrelated/pinned/linked content unless explicitly included.
3. Use typed parameter, type-replacement, transform/copy, material, grouping, or deletion tools.
   Do not use `revit_invoke_method` or `revit_reflect_set` for an ordinary type/parameter change when a typed tool exists. If a permitted raw call times out, inspect the target before retrying because Revit may already have applied it.
4. Do not ask repeatedly for explicit scope; ask once if destructive scope is still ambiguous.
5. Verify via properties, geometry, list queries, or snapshot delta; report cascades and partial failures.

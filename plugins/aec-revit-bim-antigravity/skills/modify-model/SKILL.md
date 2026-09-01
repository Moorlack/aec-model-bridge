---
name: modify-model
description: Modify, copy, move, replace, or delete live Revit elements through AEC Model Bridge.
---

Resolve targets by selection, IDs, category/type, parameter, or geometry and inspect current values. State the count and intended result. Prefer typed parameter setters, type replacement, transforms/copies, materials, groups, or deletion tools. Do not use reflection or invocation for an ordinary type/parameter change when a typed tool exists; if a permitted raw call times out, inspect the target before retrying. For destructive or broad requests, exclude unrelated, pinned, and linked content unless the user includes it; ask once only if scope remains ambiguous. Verify with properties, geometry, list queries, or snapshot delta and report cascades or partial failures.

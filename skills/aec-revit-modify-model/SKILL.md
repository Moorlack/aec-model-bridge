---
name: aec-revit-modify-model
description: Modify, copy, move, replace, or delete live Revit elements through AEC Model Bridge. Use for targeted model edits and controlled bulk changes.
---

# AEC Revit: Modify Model

Use AEC Model Bridge and start by resolving targets through selection, IDs, category/type, parameter values, or geometry. Inspect their current values and state the affected count and intended result before mutating the model.

Prefer typed setters, type replacement, transforms and copies, material changes, grouping, or deletion tools. For broad or destructive work, exclude unrelated, pinned, and linked content unless the user explicitly includes it. Ask once only when the actual target scope remains ambiguous.

Do not use `revit_invoke_method` or `revit_reflect_set` for ordinary type/parameter changes when a typed tool exists. If a permitted raw call times out, do not retry it blindly: inspect the actual target state first because Revit may have completed the mutation.

After the change, verify properties, geometry, list results, or a snapshot delta. Report cascades, unchanged targets, and partial failures. Do not treat a successful MCP response as proof that the requested Revit result exists.

---
name: aec-revit-bim
description: Work safely with a live Autodesk Revit model through AEC Model Bridge. Use for BIM design, element creation, model edits, schedules, sheets, quantities, coordination, MEP, structural work, and QA; do not use for AutoCAD or standalone files.
---

# AEC Revit BIM

Use this skill only with AEC Model Bridge and an open Revit project. Prefer the connected server's typed `revit_*` tools. Its live schema is authoritative: never invent tool names, parameters, units, loaded types, or family names.

## Start every task safely

1. Call `revit_health`, then `revit_get_document_info`.
2. Inspect only the context needed: usually `revit_list_levels`, `revit_get_selection`, `revit_list_elements`, `revit_get_elements_by_type`, or `revit_extract_snapshot`.
3. Before creation, discover viable types with `revit_get_element_type` and/or `revit_list_families`.
4. Check each creation tool's current schema before sending coordinates. State the unit conversion used; do not assume millimetres or feet.

Read the relevant playbook before acting:

- New building or a multi-stage design: [building design sequence](references/building-design-sequence.md) and [design-building](commands/design-building.md).
- A single requested object: [create-element](commands/create-element.md).
- Finding, editing, copying, moving, or deleting objects: [modify-model](commands/modify-model.md).
- Model inventory or a targeted lookup: [query-model](commands/query-model.md).
- Counts, quantities, warnings, clashes, or schedules: [analyze-model](commands/analyze-model.md).
- MEP work: [MEP workflows](references/mep-workflows.md).
- Structural work: [structural workflows](references/structural-workflows.md).
- Views, sheets, tags, dimensions, schedules, and export: [documentation workflows](references/documentation-workflows.md).
- Tool family selection: [tool routing](references/tool-routing.md).
- Units and coordinates: [unit and coordinate handling](references/unit-and-coordinate-handling.md).

## Operating rules

- Respect dependencies: levels and grids; structure where needed; enclosure and partitions; hosted openings; floors and roof; MEP/fixtures; then documentation.
- Resolve target IDs and inspect current values before mutations. For unclear geometry, hosting, or type availability, create one representative element and verify it before repeating.
- Batch only equivalent, unambiguous operations when the live tool accepts batching. Never send competing Revit mutations in parallel.
- Do not ask a separate confirmation for every line or identical element when the user has authorized an unambiguous outcome. For deletion or a project-wide change, first identify and count the scope; ask only when that scope is not already authorized.
- Use `plan_actions`, `approve_plan`, and `execute_plan` when the server's approval mode requires it or a reversible plan is appropriate. Use `rollback_plan` only for the exact plan the user asks to undo.
- For ordinary type or parameter work, do not use `revit_execute_python`, `revit_invoke_method`, or `revit_reflect_set` when a typed creation, replacement, or setter tool exists. A client timeout from a raw call can still leave Revit changed: stop, run health and a narrow read-only inspection, and never retry it blindly. Use raw API tools only when no typed tool fits and the user has authorized that extra risk.
- If bulk parameter enumeration on a system element reports that a parameter is not shared, use geometry and a targeted parameter read for the required fact; do not fall back to reflection merely to retrieve it.
- After every mutation, verify the smallest relevant result with a read-only tool, geometry/property inspection, a schedule/view, or `revit_get_snapshot_delta`. A successful request alone is not proof of success.
- Saving, syncing, relinquishing, closing, and exporting outside an approved path need explicit user authority.

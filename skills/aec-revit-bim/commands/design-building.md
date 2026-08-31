# Design building

Use this playbook for an interactive, multi-stage new-building request.

1. Extract the brief: use, footprint and units, floors/level heights, rooms, structural system, materials/style, and expected drawings. Ask only for missing facts that affect geometry or scope.
2. Confirm a live project with `revit_health` and `revit_get_document_info`; inspect levels, relevant existing elements, and loaded types.
3. Present the intended sequence and chosen available types. Then create in the order described in [building design sequence](../references/building-design-sequence.md).
4. Verify each major phase before continuing. Batch only identical, fully defined elements.
5. Produce views, tags, dimensions, schedules, sheets, and requested exports after model geometry is stable.
6. Finish with a concise inventory, QA result (warnings/clashes if relevant), and the remaining assumptions or next steps.

Do not pause for a separate approval for every wall or line if the user has approved the design. Do pause once if a missing decision materially changes the building.

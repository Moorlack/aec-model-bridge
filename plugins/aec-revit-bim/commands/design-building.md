---
description: Design a complete Revit building through AEC Model Bridge.
argument-hint: [building description]
---

Design the building described by `$ARGUMENTS` as an interactive, dependency-aware Revit workflow.

1. Gather only missing geometry-critical details: use, footprint and units, floors/level heights, rooms, structural system, materials/style, and required documentation.
2. Call `revit_health` and `revit_get_document_info`; inspect levels, existing datum, and loaded types.
3. State the intended sequence and available selected types. Create levels/grids; structure where needed; envelope and partitions; openings; floors/roof; rooms/MEP; then documentation.
4. Verify each phase before proceeding. Do not request approval for each line after the scope is clear.
5. Finish with element counts, verified QA/coordination findings, and remaining assumptions.

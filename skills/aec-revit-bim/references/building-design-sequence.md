# Building design sequence

Create a building in dependency order so that hosts, levels, documentation, and quantities remain coherent.

1. **Brief and context.** Establish use, footprint, floors, level heights, program, structural system, units, and desired deliverables. Call `revit_health`, `revit_get_document_info`, and `revit_list_levels`.
2. **Types and existing setup.** Discover appropriate loaded types with `revit_get_element_type` / `revit_list_families`; inspect existing levels, grids, and templates before adding duplicates.
3. **Datum.** Create or extend levels with `revit_create_level`; create grids with `revit_create_grid` when structural coordination needs them.
4. **Structure.** Create foundations, columns, and beams with their typed tools. Verify one bay before repeating the frame.
5. **Envelope and layout.** Create exterior walls, then partitions. Confirm each wall's level, height, and type.
6. **Openings.** Place doors and windows only after host walls are verified. Use the exact loaded family/type selected during discovery.
7. **Horizontal and top elements.** Create floors and roof from valid closed profiles; validate geometry before duplication.
8. **Rooms and systems.** Create rooms, then add ducts, pipes, conduits, fixtures, and other system elements as requested.
9. **Documentation.** Make views, sections, dimensions, tags, schedules, sheets, and viewports in that order.
10. **QA and delivery.** Inspect warnings, clashes, quantities, and snapshot changes. Export only to an approved destination.

After every major phase, state what changed and verify it. Continue without line-by-line permission prompts when the design scope is already explicit.

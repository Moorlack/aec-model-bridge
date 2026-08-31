# MEP workflows

## Start with coordination context

1. Confirm the project and level with `revit_health`, `revit_get_document_info`, and `revit_list_levels`.
2. Query relevant existing MEP and architectural/structural context before routing. Use element lists, type queries, parameters, geometry, and link tools as needed.
3. Discover usable duct, pipe, conduit, equipment, and fixture types before creation. Never invent a system/type name.

## Create and verify runs

- Use `revit_create_duct`, `revit_create_pipe`, or `revit_create_conduit` for native runs; use `revit_place_family_instance` for compatible loaded equipment or fixtures.
- Establish route endpoints, level, elevation/offset, size, and system/type from the live schema. Make a single representative segment where routing or offsets are uncertain.
- Verify created geometry and parameters, then run `revit_check_clashes` against the relevant architectural and structural scope.

## Analyze and document

- Use `revit_list_elements` / `revit_get_elements_by_type` for inventories, `revit_calculate_material_quantities` for takeoff, and `revit_create_schedule` / `revit_get_schedule_data` for deliverables.
- Use `revit_get_rvt_links` and `revit_get_link_instances` before treating linked models as editable; links are coordination context unless the user explicitly asks otherwise.
- For unsupported advanced system operations, explain the gap and use `revit_execute_python` only with specific user authorization.

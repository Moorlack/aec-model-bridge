# Tool routing

Read the connected MCP schema for exact arguments. Use `revit_health` / `revit_get_document_info` for preflight; read tools for levels, selection, elements, parameters, geometry, families, and types; `revit_create_*` / `revit_place_*` for authoring; typed parameter, transform, copy, material, group, and deletion tools for edits; and typed view, annotation, schedule, sheet, QA, quantity, link, and export tools for delivery.

Prefer `revit_create_level`, `revit_create_grid`, `revit_create_wall`, `revit_create_floor`, `revit_create_roof`, `revit_create_foundation`, `revit_create_column`, `revit_create_beam`, `revit_create_duct`, `revit_create_pipe`, `revit_create_conduit`, `revit_place_door`, `revit_place_window`, and `revit_place_family_instance` when applicable. Use `revit_execute_python`, `revit_invoke_method`, or reflection only as an approved escape hatch.

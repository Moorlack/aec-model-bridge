---
name: aec-revit-bim
description: Safely inspect, create, modify, document, and validate live Autodesk Revit models through AEC Model Bridge. Use for BIM authoring, Revit model queries, documentation, QA, quantities, and coordination; do not use for AutoCAD or standalone files.
---

# AEC Revit BIM

Use this skill only with AEC Model Bridge tools and a live Revit model. Prefer typed `revit_*` tools. The connected MCP schema is authoritative: do not invent tool names, parameters, units, or Revit family/type names.

## Preflight

Before any model operation, call `revit_health`. Then inspect the active document with `revit_get_document_info` and only the information required by the task: usually `revit_list_levels` for spatial work, or `revit_get_selection`, `revit_list_elements`, `revit_get_elements_by_type`, and `revit_extract_snapshot` for existing work.

Before creating a wall, floor, roof, door, window, structural member, MEP element, or family instance, use `revit_get_element_type` and/or `revit_list_families` to find valid loaded types. Read the tool schema before sending coordinates; convert user units to that tool's convention explicitly rather than assuming millimetres or feet.

## Authoring and edits

Follow building dependencies when the request creates a design: levels and grids; structural frame where needed; enclosure and partitions; doors/windows; floors and roof; MEP/fixtures; then views, dimensions, tags, schedules, and sheets. Use `revit_create_*` and `revit_place_*` tools for ordinary work.

For uncertain geometry, hosting, coordinate interpretation, or type availability, create one representative element and verify it before repeating. Batch only unambiguous repetitions when the connected tool supports batching. Revit operations run on its UI thread: never send conflicting mutations in parallel.

Resolve targets to IDs and inspect current values before modifications. Prefer typed tools such as `revit_set_parameter_value`, `revit_batch_set_parameters`, `revit_move_element`, `revit_rotate_element`, and `revit_change_element_type`. Do not request a separate confirmation for each element when the user has already authorized an unambiguous task.

For deletion, project-wide changes, or a modification affecting an unknown number of elements, identify IDs and count first; exclude unrelated, pinned, and linked content unless explicitly included. Seek direction only if that scope is not already authorized. Use `plan_actions`, `approve_plan`, and `execute_plan` when AEC approval mode requires it or a reversible plan is appropriate. Use `rollback_plan` only for the specific plan the user asks to reverse.

`revit_execute_python`, `revit_invoke_method`, and `revit_reflect_set` are escape hatches. Use them only when no typed tool fits and the user has authorized the specific added risk.

## Verification and delivery

After every mutation, verify the smallest relevant outcome with a read-only tool: inspect properties/geometry, query the created elements, review a schedule or view, or use `revit_get_snapshot_delta`. For coordination and QA, use `revit_get_warnings`, `revit_check_clashes`, or quantities as appropriate. Do not report success just because a request was sent.

`revit_sync_to_central`, `revit_relinquish_all`, `revit_save_document`, and `revit_close_document` affect persistence or other users; use them only when explicitly requested or clearly necessary. For exports and links, ensure paths are inside the approved workspace or explicitly provided by the user.

## Tool routing

- Read/preflight: `revit_health`, `revit_get_document_info`, `revit_list_levels`, `revit_list_elements`, `revit_get_elements_by_type`, `revit_get_selection`, `revit_get_element_type`, `revit_list_families`, `revit_get_element_parameters`, `revit_get_element_geometry`, `revit_extract_snapshot`.
- Build: `revit_create_level`, `revit_create_grid`, `revit_create_wall`, `revit_create_floor`, `revit_create_roof`, `revit_create_foundation`, `revit_create_column`, `revit_create_beam`, `revit_create_duct`, `revit_create_pipe`, `revit_create_conduit`, `revit_place_door`, `revit_place_window`, `revit_place_family_instance`.
- Document: `revit_create_3d_view`, `revit_create_floor_plan_view`, `revit_create_section_view`, `revit_create_sheet`, `revit_place_viewport_on_sheet`, `revit_create_dimension`, `revit_create_tag`, `revit_create_schedule`.
- Change: `revit_set_parameter_value`, `revit_batch_set_parameters`, `revit_set_type_parameter`, `revit_move_element`, `revit_rotate_element`, `revit_mirror_element`, `revit_copy_element`, `revit_change_element_type`, `revit_replace_family_type`, `revit_set_element_material`, `revit_delete_element`.
- Deliver/QA: `revit_get_warnings`, `revit_check_clashes`, `revit_calculate_material_quantities`, `revit_export_dwg`, `revit_export_ifc`, `revit_export_image`, `revit_export_navisworks`.

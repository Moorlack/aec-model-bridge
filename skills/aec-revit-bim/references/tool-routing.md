# AEC Model Bridge tool routing

Use the live MCP schema as the final source of argument names and supported options. This map chooses the correct *family* of tools before inspecting that schema.

| Need | Prefer |
|---|---|
| Connection and active project | `revit_health`, `revit_get_document_info` |
| Levels, selection, elements, parameters, geometry | `revit_list_levels`, `revit_get_selection`, `revit_list_elements`, `revit_get_elements_by_type`, `revit_get_element_parameters`, `revit_get_element_geometry` |
| Loaded and usable types | `revit_get_element_type`, `revit_list_families` |
| Levels and grids | `revit_create_level`, `revit_create_grid` |
| Walls, floors, roofs, rooms | `revit_create_wall`, `revit_create_floor`, `revit_create_roof`, `revit_create_room` |
| Structure | `revit_create_foundation`, `revit_create_column`, `revit_create_beam` |
| Doors, windows, other family instances | `revit_place_door`, `revit_place_window`, `revit_place_family_instance` |
| Duct, pipe, conduit | `revit_create_duct`, `revit_create_pipe`, `revit_create_conduit` |
| Parameters and types | `revit_set_parameter_value`, `revit_batch_set_parameters`, `revit_batch_set_parameters_by_filter`, `revit_set_type_parameter`, `revit_change_element_type`, `revit_replace_family_type` |
| Transform or duplicate | `revit_move_element`, `revit_rotate_element`, `revit_mirror_element`, `revit_copy_element` |
| Views and sheets | `revit_create_3d_view`, `revit_create_floor_plan_view`, `revit_create_section_view`, `revit_create_sheet`, `revit_place_viewport_on_sheet` |
| Annotation and schedules | `revit_create_dimension`, `revit_create_tag`, `revit_tag_all_in_view`, `revit_create_schedule`, `revit_create_text_note`, `revit_apply_view_template` |
| Coordination and quantities | `revit_get_warnings`, `revit_check_clashes`, `revit_calculate_material_quantities`, `revit_get_schedule_data`, `revit_get_rvt_links`, `revit_get_link_instances` |
| Export | `revit_export_dwg`, `revit_export_ifc`, `revit_export_image`, `revit_export_navisworks` |

Use raw API tools only as a last resort. Do not substitute a raw call for a typed tool merely because it looks shorter.

# Documentation workflows

## Prepare views before sheets

1. Inspect existing views and templates through the live schema.
2. Create the required 3D, plan, and section views with `revit_create_3d_view`, `revit_create_floor_plan_view`, and `revit_create_section_view`.
3. Apply a named existing template with `revit_apply_view_template` only after confirming it is the intended one.

## Annotate the verified geometry

- Add dimensions with `revit_create_dimension` only after resolving referenced elements.
- Add individual tags with `revit_create_tag` or a validated all-in-view pass with `revit_tag_all_in_view`.
- Use `revit_create_text_note` for user-specified notes, not invented construction notes.
- Create schedules with `revit_create_schedule` and inspect results with `revit_get_schedule_data`.

## Assemble and deliver

- Create sheets with `revit_create_sheet`, then place only valid views with `revit_place_viewport_on_sheet`.
- For repeated sheet sets, prefer `revit_batch_create_sheets_from_csv` when the user supplies or approves the data.
- Confirm the final sheet/view/schedule content, then export through the appropriate typed export tool to a user-approved path.

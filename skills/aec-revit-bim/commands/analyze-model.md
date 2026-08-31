# Analyze model

Use this playbook for model statistics, quantities, warnings, clashes, schedule analysis, and coordination.

1. Confirm the active document and define the analysis scope: categories, levels, linked models, or selected elements.
2. Use `revit_get_warnings`, `revit_check_clashes`, `revit_calculate_material_quantities`, `revit_get_schedule_data`, and read queries appropriate to the request.
3. Present findings as clear tables: issue/type, affected IDs or count, location/level where available, and recommended next action. Keep raw tool output out of the final answer unless it is necessary for diagnosis.
4. Do not automatically repair warnings, clashes, or quantities. Offer or perform changes only when the user requests the defined remediation.

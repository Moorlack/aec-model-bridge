# Create element

Use this playbook for a specific requested object or small set of objects.

1. Parse element kind, count, dimensions and units, level, host/position, intended type/material, and any type-specific constraints.
2. Call `revit_health`; inspect level and available type/family information needed for this object.
3. Select the typed creation tool from [tool routing](../references/tool-routing.md), then inspect its live schema before preparing arguments.
4. State the resolved object, type, level, location, and conversion. If any of those is materially ambiguous, ask one targeted question.
5. Create one sample first when hosting, geometry, or type is uncertain; otherwise create the complete unambiguous set. Verify created IDs, relevant parameters, and geometry.
6. Report what was created, including any stated default selected from loaded types.

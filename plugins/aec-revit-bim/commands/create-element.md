---
description: Create a specified Revit element through AEC Model Bridge.
argument-hint: [element description]
---

Create the object described by `$ARGUMENTS`.

1. Resolve kind, count, dimensions/units, level, host/position, requested type/material, and constraints.
2. Call `revit_health`, inspect the needed level and loaded type/family information, then choose a typed creation tool and read its live schema.
3. State the resolved type, level, placement, and unit conversion. For a requested wall or other typed system element, use the typed creation path with the resolved type when supported; do not create it and then use `revit_invoke_method` or `revit_reflect_set` merely to change type. Ask one concise question only if a material ambiguity remains.
4. Create one sample first when host/geometry/type is uncertain; otherwise create the complete unambiguous set.
5. Verify IDs, geometry, and key properties; report the actual created result.

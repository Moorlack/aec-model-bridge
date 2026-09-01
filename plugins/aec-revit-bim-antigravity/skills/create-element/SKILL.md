---
name: create-element
description: Create specified Revit elements through AEC Model Bridge from a natural-language request.
---

Resolve object kind, count, dimensions and units, level, host/position, requested type/material, and constraints. Call `revit_health`, inspect applicable levels and loaded types, select a typed creation tool, and read its live schema. State the resolved placement and conversion. For walls and other typed system elements, pass the resolved type through that typed creation path when supported rather than changing type afterward with reflection or invocation. If geometry, hosting, or type is uncertain, create and verify one representative object before repeating; otherwise create the complete unambiguous set. Report actual IDs, geometry, and key properties.

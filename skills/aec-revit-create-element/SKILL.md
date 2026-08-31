---
name: aec-revit-create-element
description: Create specified live Revit elements safely through AEC Model Bridge. Use for walls, doors, windows, floors, roofs, columns, beams, rooms, MEP objects, and other requested elements.
---

# AEC Revit: Create Element

Use AEC Model Bridge and begin with `revit_health`. Resolve the requested object kind, count, dimensions and units, level, host and placement, requested type/material, and constraints. Inspect the applicable levels and loaded types or families, then choose a typed creation tool and read its live schema.

State the resolved type, level, placement, and unit conversion. If the geometry, host, or type remains uncertain, create one representative object and verify it before repeating. Otherwise create the full unambiguous set in a suitable batch when supported.

Verify the created IDs, geometry, and important properties with a read-only tool, snapshot delta, schedule, or view. Do not invent a family name, a parameter, or coordinate convention. Do not fall back to raw Revit API tools unless no typed tool applies and the user has specifically authorized that additional risk.

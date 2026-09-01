---
name: aec-revit-query-model
description: Query a live Revit model through AEC Model Bridge without changing it. Use for element, level, family, parameter, geometry, schedule, selection, and link lookups.
---

# AEC Revit: Query Model

Confirm the bridge and document context with `revit_health` and `revit_get_document_info`, then use the narrowest read-only AEC tool that answers the request: levels, selection, elements/types, families, parameters, geometry, schedule data, snapshots, or links.

For system elements, if broad parameter enumeration reports that a parameter is not shared, use geometry and a targeted parameter-value tool for the requested fact. Do not change the model or use reflection as a query workaround.

Return compact tables containing IDs, category/type, level, and requested properties. Summarize large result sets and clearly separate Revit facts from inference. Never modify the model merely to make a query easier.

---
description: Query a live Revit model through AEC Model Bridge without modifying it.
argument-hint: [what to query]
---

Answer `$ARGUMENTS` using the narrowest read-only AEC tool.

Start with `revit_health` and document context, then query levels, selection, elements/types, parameters, geometry, families, schedules, or links as appropriate. If broad parameter enumeration on a system element reports a non-shared parameter, use geometry or a targeted parameter read for the requested fact; do not use reflection as a query workaround. Present concise, readable tables with IDs, type/category, level, and requested properties. Summarize large result sets and distinguish Revit facts from your interpretation. Do not mutate the model.

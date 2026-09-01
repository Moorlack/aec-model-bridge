---
name: query-model
description: Query a live Revit model through AEC Model Bridge without modifying it.
---

Confirm connection and document context, then use the narrowest read-only tool for levels, selection, elements/types, families, parameters, geometry, schedule data, or links. If broad parameter enumeration on a system element reports a non-shared parameter, use geometry or a targeted parameter read rather than reflection. Return compact tables with IDs, type/category, level, and requested values. Summarize large sets and distinguish Revit facts from inference. Never mutate the model as a side effect of a query.

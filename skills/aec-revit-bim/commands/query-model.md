# Query model

Use this playbook to answer an inventory, selection, type, geometry, parameter, link, or current-project question.

1. Confirm connection and document context with `revit_health` and `revit_get_document_info`.
2. Route the question to the narrowest read tool: levels, selection, element list/type, parameters, geometry, families, schedule data, or links.
3. Return a compact table with IDs, type/category, level, and only the requested key properties. For large results, summarize totals and show a representative subset.
4. Distinguish facts returned by Revit from interpretation. Do not modify the model as a side effect of a query.

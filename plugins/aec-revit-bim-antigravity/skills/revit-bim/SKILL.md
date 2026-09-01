---
name: revit-bim
description: Work safely with a live Autodesk Revit model through AEC Model Bridge. Use for BIM design, edits, documentation, quantities, MEP, structural work, and QA.
---

# AEC Revit BIM

Use the live AEC Model Bridge `revit_*` tools and treat their schema as authoritative. Start with `revit_health` and `revit_get_document_info`; inspect only required levels, elements, types, geometry, and parameters. Discover loaded types before creating. Follow dependencies: datum, structure, walls, openings, floors/roof, MEP, then documentation. Verify every mutation with a read tool, geometry/property query, schedule/view, or snapshot delta. For ordinary type/parameter work, use typed tools rather than `revit_invoke_method`, `revit_reflect_set`, or `revit_execute_python`; if a permitted raw call times out, inspect the target before any retry because Revit may already have applied it.

Do not request confirmation for each unambiguous line or element after the user has authorized the outcome. For deletion or a broad change, identify and count scope first; ask once only if it remains unclear. Use typed tools before raw API calls, and use `revit_execute_python` only for an unsupported operation with specific user authorization.

For focused workflows, use the companion skills: `design-building`, `create-element`, `modify-model`, `query-model`, and `analyze-model`. They cover the same task split as the Revit MCP Plugin: full building design, individual element placement, controlled edits, read-only investigation, and QA/quantities/coordination analysis.

For specialist work, retain the same operating standard: discover types and inspect a live schema before creating; establish units and coordinate conventions before geometry; create and verify one representative hosted or ambiguous object before repeating; and complete MEP, structural, or documentation stages only after their prerequisite model geometry is verified.

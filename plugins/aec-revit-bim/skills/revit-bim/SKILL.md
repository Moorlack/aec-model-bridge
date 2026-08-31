---
name: revit-bim
description: Work safely with a live Autodesk Revit model through AEC Model Bridge. Use for BIM design, element creation, edits, schedules, sheets, quantities, coordination, MEP, structural work, and QA.
---

# AEC Revit BIM

Use this skill with AEC Model Bridge and an open Revit project. Prefer the live server's typed `revit_*` tools. The tool schema is authoritative: never invent tool names, arguments, units, loaded types, or family names.

## Core workflow

1. Start with `revit_health` and `revit_get_document_info`.
2. Inspect only needed context: levels, selection, elements, type/family information, parameters, geometry, or a snapshot.
3. Before creation, discover usable types and inspect the selected tool's live schema, including coordinate and unit conventions.
4. Follow model dependencies: datum; structure; walls/partitions; hosted openings; floors/roof; MEP; then documentation.
5. Verify every mutation with an appropriate read tool, geometry/property query, schedule/view, or snapshot delta.

Do not ask for separate permission for every unambiguous line or instance after the user has authorized the outcome. For a deletion or wide filter, identify and count the scope first; ask once only when that scope remains unclear. Prefer typed tools; use raw Revit API tools only when a typed tool cannot do the requested work and the user has authorized that risk.

Read the relevant reference before specialized work:

- [Tool routing](references/tool-routing.md) for choosing an AEC tool family.
- [Building design sequence](references/building-design-sequence.md) for a new model.
- [MEP workflows](references/mep-workflows.md), [structural workflows](references/structural-workflows.md), or [documentation workflows](references/documentation-workflows.md) for the corresponding discipline.
- [Units and coordinates](references/unit-and-coordinate-handling.md) for every geometric request.

The plugin also exposes focused slash commands:

- `/aec-revit-bim:design-building`
- `/aec-revit-bim:create-element`
- `/aec-revit-bim:modify-model`
- `/aec-revit-bim:query-model`
- `/aec-revit-bim:analyze-model`

---
name: aec-revit-design-building
description: Design a complete live Revit building through AEC Model Bridge, from a brief through verified documentation. Use when the user asks to create or develop a building or a substantial model area.
---

# AEC Revit: Design Building

Use AEC Model Bridge with an open Revit project. Start with `revit_health` and `revit_get_document_info`; the connected server's live `revit_*` schema is authoritative.

Gather only geometry-critical missing facts: use, footprint and units, floor count and heights, required rooms, structural system, materials/style, and deliverables. Inspect existing levels, datum, and loaded types before creating anything.

Work in dependency order: levels and grids; structure where needed; exterior envelope and partitions; hosted openings; floors and roof; rooms and MEP; then views, annotations, schedules, sheets, and export. Use the typed creation and documentation tools, verify every phase, and report the verified result and remaining assumptions.

Do not ask for a separate confirmation for each wall or identical element after the requested scope is unambiguous. Ask one concise question only when an unresolved choice would materially change the model. For units and coordinate conventions, inspect the selected tool's schema rather than assuming millimetres or feet.

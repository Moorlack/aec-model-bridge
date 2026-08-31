# Structural workflows

## Establish the reference system

1. Confirm active document and levels.
2. Inspect existing grids, columns, framing, foundations, and wall types before adding elements.
3. Discover actual loaded structural types. Do not assume a concrete section, material grade, or analytical setting.

## Author in structural order

- Create datum with `revit_create_level` and `revit_create_grid` where required.
- Create supports with `revit_create_foundation` and `revit_create_column`.
- Create framing with `revit_create_beam`, confirming each member's endpoints, level, offset, and selected type.
- Use `revit_create_wall` only when structural walls are actually requested and the chosen wall type is verified.

## Validate before scaling

Create and inspect one representative foundation, column, or beam before repeating a bay. Check geometry and key parameters, then use batch parameter tools only for a known, homogeneous selection. Use `revit_check_clashes` and `revit_get_warnings` for model-level QA. If an analytical-model or specialty operation lacks a typed tool, do not improvise raw API code without explicit approval.

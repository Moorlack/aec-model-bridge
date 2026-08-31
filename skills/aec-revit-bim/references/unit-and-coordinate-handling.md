# Units and coordinates

AEC Model Bridge tool schemas can differ by operation and version. Before a geometric request, inspect the selected tool's unit and point conventions. Tell the user which convention you used if their wording could be interpreted in more than one way.

## Input discipline

- Preserve explicitly stated units: `3 m`, `3000 mm`, `10 ft`, and `12 in` are different inputs.
- If a user supplies a bare architectural dimension, do not silently guess between millimetres, metres, and feet. Use the project context or ask one concise question.
- Treat a pair such as `15 by 10` as a footprint only when the user has established a unit elsewhere.
- Keep all coordinates in the convention required by the *selected live tool*; do not mix user-facing units with Revit internal units.

## Coordinate discipline

- Use the right-hand project coordinate system required by Revit: X/Y on the plan, Z for elevation.
- Confirm the project origin, level, and orientation before placing geometry at absolute coordinates.
- For a line, name both endpoints. For a closed profile, verify closure before creating a floor or roof.
- For hosted doors/windows, confirm the intended host wall and the placement convention from the tool schema.

## Reliable defaults

Do not choose a wall, floor, family, height, material, or level merely because it is common. Discover loaded types first, then either use the user's choice or clearly state the chosen available default. For repeated work, create and verify one instance before batching the rest.

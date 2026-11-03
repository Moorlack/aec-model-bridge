# SetupMCP Revit.cmd

Windows setup for the AEC Model Bridge Revit MCP (Revit 2024-2027; Codex, Claude, Google Antigravity).
Run it as is; it requests administrator rights and updates itself from this file on `main`.

This file is generated: the AutoCAD and Revit installers share one payload maintained in
`Moorlack/best-cad-mcp/installer/SetupMCP AutoCAD.cmd`. Regenerate it with

    python installer/build_variants.py <path to this repository>

from a `best-cad-mcp` checkout instead of editing it here.

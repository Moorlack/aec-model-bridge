# SetupMCP Revit.cmd

Windows setup for the AEC Model Bridge Revit MCP (Revit 2024-2027; Codex, Claude, Google Antigravity).
Run it as is: it requests administrator rights, and at every start it compares its own
`$script:InstallerVersion` with this file on `main` and, when a newer valid version is published,
replaces itself and restarts.

This file is maintained here. To publish a change, edit it, raise the version in the three places
(`title`, `echo` and `$script:InstallerVersion`), check that the PowerShell part still parses, and push to `main`:

    $lines = Get-Content 'installer\SetupMCP Revit.cmd' -Encoding UTF8
    $m = [Array]::IndexOf($lines, '# POWERSHELL_PAYLOAD')
    $e = $null; [void][Management.Automation.Language.Parser]::ParseInput(($lines[($m+1)..($lines.Length-1)] -join "`n"), [ref]$null, [ref]$e); $e.Count

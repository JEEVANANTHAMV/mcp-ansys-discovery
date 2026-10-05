# Ansys Discovery

> Runs Ansys Discovery through this assistant instead of you opening the Ansys application by hand — it gives quick, interactive simulation feedback while a design is still being sketched out. Needs Ansys Discovery installed and licensed on this computer; the first time you use it, point it at your Ansys install folder.

The bundle is large (**99.9 MB**), above GitHub's git limit, so it is published as a **GitHub Release asset** — download it from the latest [Release](../../releases).

This repository is part of the **Forjinn-Desk** MCP bundle collection. An MCP bundle is a self-contained server that a host application launches and communicates with over the MCP (Model Context Protocol) protocol.

## Repo metadata

| Field | Value |
| --- | --- |
| Registry ID | `4ab0613f-5bcf-409f-b009-9fba339fa7ce` |
| Status in registry | active |
| Bundle size | 99.9 MB |
| Distribution | GitHub Release asset |

## Environment variables

| Variable | Value / note |
| --- | --- |
| `ANSYS_ROOT` | `C:\ANSYS\v252\ansys_inc` |

## MCP launch configuration

The host replaces `__INSTALL_DIR__` (install dir) and `__PYTHON__` (bundled Python) at runtime.

```json
{
  "command": "__PYTHON__",
  "args": [
    "server.py"
  ],
  "cwd": "__INSTALL_DIR__",
  "env": {
    "ANSYS_ROOT": "",
    "ANSYS_WORKDIR": "__INSTALL_DIR__",
    "AEDT_NO_GUI": "1"
  }
}
```


## Install / usage

1. Get the bundle:
   - download the latest release asset from the Releases tab.
2. Extract to your target installation directory (config paths expect contents at the install-dir root).
3. Set the environment variables listed above.
4. Launch using the MCP config JSON (or let a host client manage it automatically).

> Bundles may include vendored runtimes (bundled Python, Node, or native executables). Builds are Windows x64.

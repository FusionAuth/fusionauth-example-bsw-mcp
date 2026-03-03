# FusionAuth Protected MCP Server

Example code for the FusionAuth tutorial: [Protecting MCP Servers With FusionAuth OAuth](https://fusionauth.io/docs/extend/examples/protecting-mcp-servers).

This repository contains three self-contained examples:

| Folder | Description |
|--------|-------------|
| `unprotected-local-mcp/` | Starter code — a simple MCP server with no authentication. Start here if following the tutorial. |
| `protected-local-mcp/` | Completed code — the same MCP server with FusionAuth OAuth protection added. |
| `protected-remote-mcp/` | Remote deployment variant — extends the protected server with flags for deploying to a public URL. |

Each folder contains its own `docker-compose.yml`, `kickstart/`, `mcp-server/`, and `setup/` directories and can be run independently.

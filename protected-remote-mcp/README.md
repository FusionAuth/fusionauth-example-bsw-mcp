# Protected Remote MCP Server

Remote deployment variant for the FusionAuth tutorial: [Protecting MCP Servers With FusionAuth OAuth](https://fusionauth.io/docs/extend/examples/protecting-mcp-servers).

This extends the completed local example with support for deploying the MCP server to a public URL. The setup script includes `--tenant-id`, `--mcp-server-url`, and `--connector-ui` flags for remote deployments.

## Prerequisites

- Docker Desktop (for local FusionAuth) or a hosted FusionAuth instance
- A publicly accessible URL for the MCP server (e.g. via Fly.io or ngrok)
- Node.js >= 20.18.1
- Python 3.12+
- FusionAuth Essentials license (required for custom OAuth scopes)

## Quick Start

### 1. Deploy the MCP server

Deploy `mcp-server/` to your hosting platform of choice. The `MCP_SERVER_URL` environment variable must be set to the public URL of the deployed server.

### 2. Configure FusionAuth

Point FusionAuth at your deployed server by setting `MCP_SERVER_URL` in `docker-compose.yml`, or use a hosted FusionAuth instance.

### 3. Register an MCP client

```bash
cd setup
pip install -r requirements.txt
python setup_clients.py --mcp-server-url https://your-mcp-server.example.com --tenant-id YOUR_TENANT_ID
```

For the Claude Desktop or claude.ai connector UI, add `--connector-ui`:

```bash
python setup_clients.py --mcp-server-url https://your-mcp-server.example.com --tenant-id YOUR_TENANT_ID --connector-ui
```

### 4. Connect your MCP client

Use the configuration output from step 3. See the full tutorial for client-specific instructions.

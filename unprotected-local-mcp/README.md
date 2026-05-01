# Unprotected Local MCP Server

This is a minimal MCP server with a single `get_name` tool and no authentication.

## Prerequisites

- Docker Desktop
- Node.js >= 20.18.1
- Python 3.12+
- FusionAuth Essentials license (required for custom OAuth scopes)

## Quick Start

### 1. Configure your license

Open `kickstart/kickstart.json` and replace `YOUR_LICENSE_KEY_HERE` with your FusionAuth Essentials license key.

### 2. Start the stack

```bash
docker compose up -d
```

Wait about 30 seconds for all services to start.

### 3. Test the unprotected server

```bash
curl -X POST http://localhost:8000/mcp \
  -H "Content-Type: application/json" \
  -H "Accept: application/json, text/event-stream" \
  -d '{
    "jsonrpc": "2.0",
    "id": 1,
    "method": "tools/call",
    "params": {
      "name": "get_name",
      "arguments": {}
    }
  }'
```

You should see `Hello, World!` in the response.

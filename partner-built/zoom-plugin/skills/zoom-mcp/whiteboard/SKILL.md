---
name: zoom-mcp-whiteboard
description: |
  Guidance for the bundled Zoom Whiteboard MCP connector. Use for Whiteboard MCP auth,
  endpoints, ID mapping, and tool workflows such as list_whiteboards and get_a_whiteboard.
  Prefer this skill when the request is specifically about Whiteboard MCP rather than general Zoom MCP.
user-invocable: false
triggers:
  - "whiteboard mcp"
  - "zoom whiteboard mcp"
  - "zoom mcp whiteboard"
  - "zoom whiteboard tools"
  - "list zoom whiteboards"
  - "get zoom whiteboard"
  - "zoom whiteboard id"
  - "zoom wb/db"
---

# Zoom MCP Whiteboard

Dedicated guidance for Zoom's Whiteboard MCP server.

## Endpoints

| Transport | URL |
|-----------|-----|
| Streamable HTTP (recommended) | `https://mcp-us.zoom.us/mcp/whiteboard/streamable` |
| SSE (fallback) | `https://mcp-us.zoom.us/mcp/whiteboard/sse` |

## Authentication

- **User OAuth with Whiteboard scopes** is the verified working path for `list_whiteboards`
  and `get_a_whiteboard`.
- **S2S OAuth** can reach the Whiteboard MCP gateway and complete `tools/list`, but tool
  execution must be validated separately for your app and Whiteboard scopes.
- Practical rule: start with **user OAuth** for Whiteboard MCP unless you have already
  proven your S2S app can mint and execute with the required Whiteboard scopes.
- The bundled connector expects the token in `ZOOM_WHITEBOARD_MCP_ACCESS_TOKEN`.

Reference: [references/authentication-and-identifiers.md](references/authentication-and-identifiers.md)

## Required Scopes

Whiteboard MCP read scopes:
- `whiteboard:read:list_whiteboards`
- `whiteboard:read:whiteboard`

Write-capable Whiteboard metadata advertised by the gateway:
- `whiteboard:write:whiteboard`

## Whiteboard ID Mapping

For Whiteboard MCP, use the identifier from the URL segment after `/wb/db/`, not the numeric
segment after `/p/`.

# Create Workspace

Create a new workspace within the organization with a specified name and display color.

## API Details

- **API**: Anthropic Administrative API
- **Method**: POST
- **Path**: `/organizations/workspaces`
- **Operation ID**: `createWorkspace`
- **OpenAPI**: [anthropic-admin-api-openapi.yml](../../openapi/anthropic-admin-api-openapi.yml)

## Sandbox

Mock server URL: `http://localhost:8080/rest/anthropic-admin-api/1.0.0/organizations/workspaces`

## Required Headers

- `anthropic-version: 2023-06-01`
- `x-api-key: {admin-api-key}`
- `Content-Type: application/json`

## Request Body

```json
{
  "name": "My New Workspace",
  "display_color": "#4287f5"
}
```

| Field | Type | Required | Description |
|-------|------|----------|-------------|
| `name` | string | Yes | Name for the new workspace |
| `display_color` | string | No | Hex color code for the workspace display |

## Example Request

```bash
curl -X POST "http://localhost:8080/rest/anthropic-admin-api/1.0.0/organizations/workspaces" \
  -H "anthropic-version: 2023-06-01" \
  -H "x-api-key: your-admin-api-key" \
  -H "Content-Type: application/json" \
  -d '{"name": "My New Workspace", "display_color": "#4287f5"}'
```

## Example Response

```json
{
  "id": "wrkspc_01SomeWorkspaceId",
  "type": "workspace",
  "name": "My New Workspace",
  "display_color": "#4287f5",
  "is_default": false,
  "created_at": "2024-11-07T05:31:56Z",
  "archived_at": null
}
```

## Instructions

When the user asks to create a new workspace, use this operation by making a POST request to `/organizations/workspaces` with the workspace name and optional display color.

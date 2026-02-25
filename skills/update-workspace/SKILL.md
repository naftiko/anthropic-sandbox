# Update Workspace

Update the name or display color of an existing workspace.

## API Details

- **API**: Anthropic Administrative API
- **Method**: POST
- **Path**: `/organizations/workspaces/{workspace_id}`
- **Operation ID**: `updateWorkspace`
- **OpenAPI**: [anthropic-admin-api-openapi.yml](../../openapi/anthropic-admin-api-openapi.yml)

## Sandbox

Mock server URL: `http://localhost:8080/rest/anthropic-admin-api/1.0.0/organizations/workspaces/{workspace_id}`

## Required Headers

- `anthropic-version: 2023-06-01`
- `x-api-key: {admin-api-key}`
- `Content-Type: application/json`

## Path Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `workspace_id` | string | Yes | Unique identifier of the workspace to update |

## Request Body

```json
{
  "name": "Updated Workspace Name"
}
```

| Field | Type | Required | Description |
|-------|------|----------|-------------|
| `name` | string | No | New name for the workspace |
| `display_color` | string | No | New hex color code for display |

## Example Request

```bash
curl -X POST "http://localhost:8080/rest/anthropic-admin-api/1.0.0/organizations/workspaces/wrkspc_01SomeWorkspaceId" \
  -H "anthropic-version: 2023-06-01" \
  -H "x-api-key: your-admin-api-key" \
  -H "Content-Type: application/json" \
  -d '{"name": "Updated Workspace Name"}'
```

## Example Response

```json
{
  "id": "wrkspc_01SomeWorkspaceId",
  "type": "workspace",
  "name": "Updated Workspace Name",
  "display_color": "#FF5733",
  "is_default": false,
  "created_at": "2024-01-15T10:00:00Z",
  "archived_at": null
}
```

## Instructions

When the user asks to update or rename a workspace, use this operation by making a POST request to `/organizations/workspaces/{workspace_id}` with the fields to update.

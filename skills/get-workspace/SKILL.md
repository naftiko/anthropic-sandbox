# Get Workspace

Retrieve detailed information about a specific workspace by its ID.

## API Details

- **API**: Anthropic Administrative API
- **Method**: GET
- **Path**: `/organizations/workspaces/{workspace_id}`
- **Operation ID**: `getWorkspace`
- **OpenAPI**: [anthropic-admin-api-openapi.yml](../../openapi/anthropic-admin-api-openapi.yml)

## Sandbox

Mock server URL: `http://localhost:8080/rest/anthropic-admin-api/1.0.0/organizations/workspaces/{workspace_id}`

## Required Headers

- `anthropic-version: 2023-06-01`
- `x-api-key: {admin-api-key}`

## Path Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `workspace_id` | string | Yes | Unique identifier of the workspace |

## Example Request

```bash
curl -X GET "http://localhost:8080/rest/anthropic-admin-api/1.0.0/organizations/workspaces/wrkspc_01SomeWorkspaceId" \
  -H "anthropic-version: 2023-06-01" \
  -H "x-api-key: your-admin-api-key"
```

## Example Response

```json
{
  "id": "wrkspc_01SomeWorkspaceId",
  "type": "workspace",
  "name": "Production",
  "display_color": "#FF5733",
  "is_default": true,
  "created_at": "2024-01-15T10:00:00Z",
  "archived_at": null
}
```

## Instructions

When the user asks to get or view a specific workspace by ID, use this operation by making a GET request to `/organizations/workspaces/{workspace_id}`.

# Archive Workspace

Archive a workspace, making it inactive and hidden from default listings. Archived workspaces can optionally be restored.

## API Details

- **API**: Anthropic Administrative API
- **Method**: POST
- **Path**: `/organizations/workspaces/{workspace_id}/archive`
- **Operation ID**: `archiveWorkspace`
- **OpenAPI**: [anthropic-admin-api-openapi.yml](../../openapi/anthropic-admin-api-openapi.yml)

## Sandbox

Mock server URL: `http://localhost:8080/rest/anthropic-admin-api/1.0.0/organizations/workspaces/{workspace_id}/archive`

## Required Headers

- `anthropic-version: 2023-06-01`
- `x-api-key: {admin-api-key}`

## Path Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `workspace_id` | string | Yes | Unique identifier of the workspace to archive |

## Example Request

```bash
curl -X POST "http://localhost:8080/rest/anthropic-admin-api/1.0.0/organizations/workspaces/wrkspc_01SomeWorkspaceId/archive" \
  -H "anthropic-version: 2023-06-01" \
  -H "x-api-key: your-admin-api-key"
```

## Example Response

```json
{
  "id": "wrkspc_01SomeWorkspaceId",
  "type": "workspace",
  "name": "Old Project",
  "display_color": "#FF5733",
  "is_default": false,
  "created_at": "2024-01-15T10:00:00Z",
  "archived_at": "2024-11-07T05:31:56Z"
}
```

## Instructions

When the user asks to archive or deactivate a workspace, use this operation by making a POST request to `/organizations/workspaces/{workspace_id}/archive`. Note that the default workspace cannot be archived.

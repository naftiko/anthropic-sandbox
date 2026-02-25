# List Workspaces

Retrieve a paginated list of workspaces within the organization, with an option to include archived workspaces.

## API Details

- **API**: Anthropic Administrative API
- **Method**: GET
- **Path**: `/organizations/workspaces`
- **Operation ID**: `listWorkspaces`
- **OpenAPI**: [anthropic-admin-api-openapi.yml](../../openapi/anthropic-admin-api-openapi.yml)

## Sandbox

Mock server URL: `http://localhost:8080/rest/anthropic-admin-api/1.0.0/organizations/workspaces`

## Required Headers

- `anthropic-version: 2023-06-01`
- `x-api-key: {admin-api-key}`

## Query Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `limit` | integer | No | Items per page (1-1000, default 20) |
| `before_id` | string | No | Cursor for previous page |
| `after_id` | string | No | Cursor for next page |
| `include_archived` | boolean | No | Include archived workspaces (default false) |

## Example Request

```bash
curl -X GET "http://localhost:8080/rest/anthropic-admin-api/1.0.0/organizations/workspaces" \
  -H "anthropic-version: 2023-06-01" \
  -H "x-api-key: your-admin-api-key"
```

## Example Response

```json
{
  "data": [
    {
      "id": "wrkspc_01SomeWorkspaceId",
      "type": "workspace",
      "name": "Production",
      "display_color": "#FF5733",
      "is_default": true,
      "created_at": "2024-01-15T10:00:00Z",
      "archived_at": null
    }
  ],
  "first_id": "wrkspc_01SomeWorkspaceId",
  "has_more": false,
  "last_id": "wrkspc_01SomeWorkspaceId"
}
```

## Instructions

When the user asks to list or view workspaces in the organization, use this operation by making a GET request to `/organizations/workspaces`. Add `include_archived=true` if the user wants to see archived workspaces as well.

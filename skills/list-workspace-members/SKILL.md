# List Workspace Members

Retrieve a paginated list of all members in a specific workspace.

## API Details

- **API**: Anthropic Administrative API
- **Method**: GET
- **Path**: `/organizations/workspaces/{workspace_id}/members`
- **Operation ID**: `listWorkspaceMembers`
- **OpenAPI**: [anthropic-admin-api-openapi.yml](../../openapi/anthropic-admin-api-openapi.yml)

## Sandbox

Mock server URL: `http://localhost:8080/rest/anthropic-admin-api/1.0.0/organizations/workspaces/{workspace_id}/members`

## Required Headers

- `anthropic-version: 2023-06-01`
- `x-api-key: {admin-api-key}`

## Path Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `workspace_id` | string | Yes | Unique identifier of the workspace |

## Query Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `limit` | integer | No | Items per page (1-1000, default 20) |
| `before_id` | string | No | Cursor for previous page |
| `after_id` | string | No | Cursor for next page |

## Example Request

```bash
curl -X GET "http://localhost:8080/rest/anthropic-admin-api/1.0.0/organizations/workspaces/wrkspc_01SomeWorkspaceId/members" \
  -H "anthropic-version: 2023-06-01" \
  -H "x-api-key: your-admin-api-key"
```

## Example Response

```json
{
  "data": [
    {
      "type": "workspace_member",
      "user_id": "user_01WCz1FkmYMm4gnmyk7nteBY",
      "workspace_id": "wrkspc_01SomeWorkspaceId",
      "workspace_role": "workspace_developer"
    }
  ],
  "first_id": "user_01WCz1FkmYMm4gnmyk7nteBY",
  "has_more": false,
  "last_id": "user_01WCz1FkmYMm4gnmyk7nteBY"
}
```

## Instructions

When the user asks to list members of a specific workspace, use this operation by making a GET request to `/organizations/workspaces/{workspace_id}/members`.

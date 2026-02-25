# Get Workspace Member

Retrieve details about a specific user's membership in a workspace, including their workspace role.

## API Details

- **API**: Anthropic Administrative API
- **Method**: GET
- **Path**: `/organizations/workspaces/{workspace_id}/members/{user_id}`
- **Operation ID**: `getWorkspaceMember`
- **OpenAPI**: [anthropic-admin-api-openapi.yml](../../openapi/anthropic-admin-api-openapi.yml)

## Sandbox

Mock server URL: `http://localhost:8080/rest/anthropic-admin-api/1.0.0/organizations/workspaces/{workspace_id}/members/{user_id}`

## Required Headers

- `anthropic-version: 2023-06-01`
- `x-api-key: {admin-api-key}`

## Path Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `workspace_id` | string | Yes | Unique identifier of the workspace |
| `user_id` | string | Yes | Unique identifier of the user |

## Example Request

```bash
curl -X GET "http://localhost:8080/rest/anthropic-admin-api/1.0.0/organizations/workspaces/wrkspc_01SomeWorkspaceId/members/user_01WCz1FkmYMm4gnmyk7nteBY" \
  -H "anthropic-version: 2023-06-01" \
  -H "x-api-key: your-admin-api-key"
```

## Example Response

```json
{
  "type": "workspace_member",
  "user_id": "user_01WCz1FkmYMm4gnmyk7nteBY",
  "workspace_id": "wrkspc_01SomeWorkspaceId",
  "workspace_role": "workspace_developer"
}
```

## Instructions

When the user asks to get details about a specific member in a workspace, use this operation by making a GET request to `/organizations/workspaces/{workspace_id}/members/{user_id}`.

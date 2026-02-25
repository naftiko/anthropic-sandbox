# Update Workspace Member

Update the workspace role of a specific member within a workspace.

## API Details

- **API**: Anthropic Administrative API
- **Method**: POST
- **Path**: `/organizations/workspaces/{workspace_id}/members/{user_id}`
- **Operation ID**: `updateWorkspaceMember`
- **OpenAPI**: [anthropic-admin-api-openapi.yml](../../openapi/anthropic-admin-api-openapi.yml)

## Sandbox

Mock server URL: `http://localhost:8080/rest/anthropic-admin-api/1.0.0/organizations/workspaces/{workspace_id}/members/{user_id}`

## Required Headers

- `anthropic-version: 2023-06-01`
- `x-api-key: {admin-api-key}`
- `Content-Type: application/json`

## Path Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `workspace_id` | string | Yes | Unique identifier of the workspace |
| `user_id` | string | Yes | Unique identifier of the user |

## Request Body

```json
{
  "workspace_role": "workspace_admin"
}
```

| Field | Type | Required | Description |
|-------|------|----------|-------------|
| `workspace_role` | string | Yes | New role for the workspace member |

## Example Request

```bash
curl -X POST "http://localhost:8080/rest/anthropic-admin-api/1.0.0/organizations/workspaces/wrkspc_01SomeWorkspaceId/members/user_01WCz1FkmYMm4gnmyk7nteBY" \
  -H "anthropic-version: 2023-06-01" \
  -H "x-api-key: your-admin-api-key" \
  -H "Content-Type: application/json" \
  -d '{"workspace_role": "workspace_admin"}'
```

## Example Response

```json
{
  "type": "workspace_member",
  "user_id": "user_01WCz1FkmYMm4gnmyk7nteBY",
  "workspace_id": "wrkspc_01SomeWorkspaceId",
  "workspace_role": "workspace_admin"
}
```

## Instructions

When the user asks to change or update a workspace member's role, use this operation by making a POST request to `/organizations/workspaces/{workspace_id}/members/{user_id}` with the new role.

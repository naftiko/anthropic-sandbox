# Add Workspace Member

Add an existing organization member to a specific workspace with a designated role.

## API Details

- **API**: Anthropic Administrative API
- **Method**: POST
- **Path**: `/organizations/workspaces/{workspace_id}/members`
- **Operation ID**: `addWorkspaceMember`
- **OpenAPI**: [anthropic-admin-api-openapi.yml](../../openapi/anthropic-admin-api-openapi.yml)

## Sandbox

Mock server URL: `http://localhost:8080/rest/anthropic-admin-api/1.0.0/organizations/workspaces/{workspace_id}/members`

## Required Headers

- `anthropic-version: 2023-06-01`
- `x-api-key: {admin-api-key}`
- `Content-Type: application/json`

## Path Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `workspace_id` | string | Yes | Unique identifier of the workspace |

## Request Body

```json
{
  "user_id": "user_01WCz1FkmYMm4gnmyk7nteBY",
  "workspace_role": "workspace_developer"
}
```

| Field | Type | Required | Description |
|-------|------|----------|-------------|
| `user_id` | string | Yes | ID of the user to add |
| `workspace_role` | string | Yes | Role in workspace (e.g., `workspace_admin`, `workspace_developer`, `workspace_viewer`) |

## Example Request

```bash
curl -X POST "http://localhost:8080/rest/anthropic-admin-api/1.0.0/organizations/workspaces/wrkspc_01SomeWorkspaceId/members" \
  -H "anthropic-version: 2023-06-01" \
  -H "x-api-key: your-admin-api-key" \
  -H "Content-Type: application/json" \
  -d '{"user_id": "user_01WCz1FkmYMm4gnmyk7nteBY", "workspace_role": "workspace_developer"}'
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

When the user asks to add a user to a workspace, use this operation by making a POST request to `/organizations/workspaces/{workspace_id}/members` with the user ID and workspace role.

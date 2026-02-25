# Remove Organization Member

Permanently remove a specific user from the organization. This revokes all their access to the organization and its workspaces.

## API Details

- **API**: Anthropic Administrative API
- **Method**: DELETE
- **Path**: `/organizations/users/{user_id}`
- **Operation ID**: `removeOrganizationMember`
- **OpenAPI**: [anthropic-admin-api-openapi.yml](../../openapi/anthropic-admin-api-openapi.yml)

## Sandbox

Mock server URL: `http://localhost:8080/rest/anthropic-admin-api/1.0.0/organizations/users/{user_id}`

## Required Headers

- `anthropic-version: 2023-06-01`
- `x-api-key: {admin-api-key}`

## Path Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `user_id` | string | Yes | Unique identifier of the user to remove |

## Example Request

```bash
curl -X DELETE "http://localhost:8080/rest/anthropic-admin-api/1.0.0/organizations/users/user_01WCz1FkmYMm4gnmyk7nteBY" \
  -H "anthropic-version: 2023-06-01" \
  -H "x-api-key: your-admin-api-key"
```

## Example Response

```json
{
  "id": "user_01WCz1FkmYMm4gnmyk7nteBY",
  "type": "user_deleted"
}
```

## Instructions

When the user asks to remove or delete an organization member, use this operation by making a DELETE request to `/organizations/users/{user_id}`. Confirm the user ID before executing. This action is irreversible.

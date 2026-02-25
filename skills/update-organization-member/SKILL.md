# Update Organization Member

Update the role or other attributes of a specific user within the organization.

## API Details

- **API**: Anthropic Administrative API
- **Method**: POST
- **Path**: `/organizations/users/{user_id}`
- **Operation ID**: `updateOrganizationMember`
- **OpenAPI**: [anthropic-admin-api-openapi.yml](../../openapi/anthropic-admin-api-openapi.yml)

## Sandbox

Mock server URL: `http://localhost:8080/rest/anthropic-admin-api/1.0.0/organizations/users/{user_id}`

## Required Headers

- `anthropic-version: 2023-06-01`
- `x-api-key: {admin-api-key}`
- `Content-Type: application/json`

## Path Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `user_id` | string | Yes | Unique identifier of the user to update |

## Request Body

```json
{
  "role": "user"
}
```

| Field | Type | Required | Description |
|-------|------|----------|-------------|
| `role` | string | No | New role for the user (e.g., `admin`, `user`) |

## Example Request

```bash
curl -X POST "http://localhost:8080/rest/anthropic-admin-api/1.0.0/organizations/users/user_01WCz1FkmYMm4gnmyk7nteBY" \
  -H "anthropic-version: 2023-06-01" \
  -H "x-api-key: your-admin-api-key" \
  -H "Content-Type: application/json" \
  -d '{"role": "user"}'
```

## Example Response

```json
{
  "id": "user_01WCz1FkmYMm4gnmyk7nteBY",
  "type": "user",
  "email": "jane@example.com",
  "name": "Jane Smith",
  "role": "user"
}
```

## Instructions

When the user asks to update an organization member's role or attributes, use this operation by making a POST request to `/organizations/users/{user_id}` with the updated fields in the request body.

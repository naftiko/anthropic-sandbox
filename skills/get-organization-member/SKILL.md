# Get Organization Member

Retrieve detailed information about a specific user within the organization by their user ID.

## API Details

- **API**: Anthropic Administrative API
- **Method**: GET
- **Path**: `/organizations/users/{user_id}`
- **Operation ID**: `getOrganizationMember`
- **OpenAPI**: [anthropic-admin-api-openapi.yml](../../openapi/anthropic-admin-api-openapi.yml)

## Sandbox

Mock server URL: `http://localhost:8080/rest/anthropic-admin-api/1.0.0/organizations/users/{user_id}`

## Required Headers

- `anthropic-version: 2023-06-01`
- `x-api-key: {admin-api-key}`

## Path Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `user_id` | string | Yes | Unique identifier of the user |

## Example Request

```bash
curl -X GET "http://localhost:8080/rest/anthropic-admin-api/1.0.0/organizations/users/user_01WCz1FkmYMm4gnmyk7nteBY" \
  -H "anthropic-version: 2023-06-01" \
  -H "x-api-key: your-admin-api-key"
```

## Example Response

```json
{
  "id": "user_01WCz1FkmYMm4gnmyk7nteBY",
  "type": "user",
  "email": "jane@example.com",
  "name": "Jane Smith",
  "role": "admin"
}
```

## Instructions

When the user asks to get or view a specific organization member by ID, use this operation by making a GET request to `/organizations/users/{user_id}`. Replace `{user_id}` with the actual user identifier provided by the user.

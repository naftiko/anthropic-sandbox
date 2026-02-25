# List Organization Members

Retrieve a paginated list of all users associated with the organization, with optional filtering by email address.

## API Details

- **API**: Anthropic Administrative API
- **Method**: GET
- **Path**: `/organizations/users`
- **Operation ID**: `listOrganizationMembers`
- **OpenAPI**: [anthropic-admin-api-openapi.yml](../../openapi/anthropic-admin-api-openapi.yml)

## Sandbox

Mock server URL: `http://localhost:8080/rest/anthropic-admin-api/1.0.0/organizations/users`

## Required Headers

- `anthropic-version: 2023-06-01`
- `x-api-key: {admin-api-key}`

## Query Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `limit` | integer | No | Items per page (1-1000, default 20) |
| `before_id` | string | No | Cursor for previous page |
| `after_id` | string | No | Cursor for next page |
| `email` | string | No | Filter by user email address |

## Example Request

```bash
curl -X GET "http://localhost:8080/rest/anthropic-admin-api/1.0.0/organizations/users?limit=20" \
  -H "anthropic-version: 2023-06-01" \
  -H "x-api-key: your-admin-api-key"
```

## Example Response

```json
{
  "data": [
    {
      "id": "user_01WCz1FkmYMm4gnmyk7nteBY",
      "type": "user",
      "email": "jane@example.com",
      "name": "Jane Smith",
      "role": "admin"
    }
  ],
  "first_id": "user_01WCz1FkmYMm4gnmyk7nteBY",
  "has_more": false,
  "last_id": "user_01WCz1FkmYMm4gnmyk7nteBY"
}
```

## Instructions

When the user asks to list or view organization members or users, use this operation by making a GET request to `/organizations/users`. Support pagination using `before_id`/`after_id` cursors and filtering by `email` if specified.

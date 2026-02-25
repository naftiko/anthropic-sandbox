# List Organization Invites

Retrieve a paginated list of all pending invitations for the organization.

## API Details

- **API**: Anthropic Administrative API
- **Method**: GET
- **Path**: `/organizations/invites`
- **Operation ID**: `listOrganizationInvites`
- **OpenAPI**: [anthropic-admin-api-openapi.yml](../../openapi/anthropic-admin-api-openapi.yml)

## Sandbox

Mock server URL: `http://localhost:8080/rest/anthropic-admin-api/1.0.0/organizations/invites`

## Required Headers

- `anthropic-version: 2023-06-01`
- `x-api-key: {admin-api-key}`

## Query Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `limit` | integer | No | Items per page (1-1000, default 20) |
| `before_id` | string | No | Cursor for previous page |
| `after_id` | string | No | Cursor for next page |

## Example Request

```bash
curl -X GET "http://localhost:8080/rest/anthropic-admin-api/1.0.0/organizations/invites" \
  -H "anthropic-version: 2023-06-01" \
  -H "x-api-key: your-admin-api-key"
```

## Example Response

```json
{
  "data": [
    {
      "id": "invite_01XWRAFVJwHk3PNPkuoXwvFD",
      "type": "invite",
      "email": "newuser@example.com",
      "role": "user",
      "status": "pending",
      "expires_at": "2024-12-31T23:59:59Z"
    }
  ],
  "first_id": "invite_01XWRAFVJwHk3PNPkuoXwvFD",
  "has_more": false,
  "last_id": "invite_01XWRAFVJwHk3PNPkuoXwvFD"
}
```

## Instructions

When the user asks to list or view pending organization invitations, use this operation by making a GET request to `/organizations/invites`. Support pagination using cursor parameters.

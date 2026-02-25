# Get Organization Invite

Retrieve detailed information about a specific organization invitation by its invite ID.

## API Details

- **API**: Anthropic Administrative API
- **Method**: GET
- **Path**: `/organizations/invites/{invite_id}`
- **Operation ID**: `getOrganizationInvite`
- **OpenAPI**: [anthropic-admin-api-openapi.yml](../../openapi/anthropic-admin-api-openapi.yml)

## Sandbox

Mock server URL: `http://localhost:8080/rest/anthropic-admin-api/1.0.0/organizations/invites/{invite_id}`

## Required Headers

- `anthropic-version: 2023-06-01`
- `x-api-key: {admin-api-key}`

## Path Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `invite_id` | string | Yes | Unique identifier of the invite |

## Example Request

```bash
curl -X GET "http://localhost:8080/rest/anthropic-admin-api/1.0.0/organizations/invites/invite_01XWRAFVJwHk3PNPkuoXwvFD" \
  -H "anthropic-version: 2023-06-01" \
  -H "x-api-key: your-admin-api-key"
```

## Example Response

```json
{
  "id": "invite_01XWRAFVJwHk3PNPkuoXwvFD",
  "type": "invite",
  "email": "newuser@example.com",
  "role": "user",
  "status": "pending",
  "expires_at": "2024-12-31T23:59:59Z"
}
```

## Instructions

When the user asks to get or view a specific organization invite by ID, use this operation by making a GET request to `/organizations/invites/{invite_id}`. Replace `{invite_id}` with the actual invite identifier.

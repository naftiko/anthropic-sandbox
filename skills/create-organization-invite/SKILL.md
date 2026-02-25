# Create Organization Invite

Send an invitation to a new user to join the organization with a specified role.

## API Details

- **API**: Anthropic Administrative API
- **Method**: POST
- **Path**: `/organizations/invites`
- **Operation ID**: `createOrganizationInvite`
- **OpenAPI**: [anthropic-admin-api-openapi.yml](../../openapi/anthropic-admin-api-openapi.yml)

## Sandbox

Mock server URL: `http://localhost:8080/rest/anthropic-admin-api/1.0.0/organizations/invites`

## Required Headers

- `anthropic-version: 2023-06-01`
- `x-api-key: {admin-api-key}`
- `Content-Type: application/json`

## Request Body

```json
{
  "email": "newuser@example.com",
  "role": "user"
}
```

| Field | Type | Required | Description |
|-------|------|----------|-------------|
| `email` | string | Yes | Email address of the person to invite |
| `role` | string | Yes | Role to assign (`admin` or `user`) |

## Example Request

```bash
curl -X POST "http://localhost:8080/rest/anthropic-admin-api/1.0.0/organizations/invites" \
  -H "anthropic-version: 2023-06-01" \
  -H "x-api-key: your-admin-api-key" \
  -H "Content-Type: application/json" \
  -d '{"email": "newuser@example.com", "role": "user"}'
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

When the user asks to invite someone to the organization, use this operation by making a POST request to `/organizations/invites` with the recipient's email and desired role.

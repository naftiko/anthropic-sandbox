# Delete Organization Invite

Delete a specific organization invitation, preventing the recipient from accepting it.

## API Details

- **API**: Anthropic Administrative API
- **Method**: DELETE
- **Path**: `/organizations/invites/{invite_id}`
- **Operation ID**: `deleteOrganizationInvite`
- **OpenAPI**: [anthropic-admin-api-openapi.yml](../../openapi/anthropic-admin-api-openapi.yml)

## Sandbox

Mock server URL: `http://localhost:8080/rest/anthropic-admin-api/1.0.0/organizations/invites/{invite_id}`

## Required Headers

- `anthropic-version: 2023-06-01`
- `x-api-key: {admin-api-key}`

## Path Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `invite_id` | string | Yes | Unique identifier of the invite to delete |

## Example Request

```bash
curl -X DELETE "http://localhost:8080/rest/anthropic-admin-api/1.0.0/organizations/invites/invite_01XWRAFVJwHk3PNPkuoXwvFD" \
  -H "anthropic-version: 2023-06-01" \
  -H "x-api-key: your-admin-api-key"
```

## Example Response

```json
{
  "id": "invite_01XWRAFVJwHk3PNPkuoXwvFD",
  "type": "invite_deleted"
}
```

## Instructions

When the user asks to delete or cancel an organization invite, use this operation by making a DELETE request to `/organizations/invites/{invite_id}`. This action permanently revokes the invitation.

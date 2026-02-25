# Get Current Organization

Retrieve information about the current authenticated user's organization, including organization name, ID, settings, and billing details.

## API Details

- **API**: Anthropic Administrative API
- **Method**: GET
- **Path**: `/organizations/me`
- **Operation ID**: `getCurrentOrganization`
- **OpenAPI**: [anthropic-admin-api-openapi.yml](../../openapi/anthropic-admin-api-openapi.yml)

## Sandbox

Mock server URL: `http://localhost:8080/rest/anthropic-admin-api/1.0.0/organizations/me`

## Required Headers

- `anthropic-version: 2023-06-01`
- `x-api-key: {admin-api-key}`

## Example Request

```bash
curl -X GET "http://localhost:8080/rest/anthropic-admin-api/1.0.0/organizations/me" \
  -H "anthropic-version: 2023-06-01" \
  -H "x-api-key: your-admin-api-key"
```

## Example Response

```json
{
  "id": "org_01JwR2xCNyBsYcMb4t1pxmUP",
  "type": "organization",
  "name": "Acme Corp",
  "billing_email": "billing@acme.com"
}
```

## Instructions

When the user asks to get or view their current organization information, use this operation by making a GET request to `/organizations/me` with an admin API key. Return the organization details including its ID, name, and billing information.

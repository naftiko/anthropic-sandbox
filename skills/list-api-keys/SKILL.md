# List API Keys

Retrieve a paginated list of all API keys associated with the organization, with optional filtering by workspace and status.

## API Details

- **API**: Anthropic Administrative API
- **Method**: GET
- **Path**: `/organizations/api_keys`
- **Operation ID**: `listApiKeys`
- **OpenAPI**: [anthropic-admin-api-openapi.yml](../../openapi/anthropic-admin-api-openapi.yml)

## Sandbox

Mock server URL: `http://localhost:8080/rest/anthropic-admin-api/1.0.0/organizations/api_keys`

## Required Headers

- `anthropic-version: 2023-06-01`
- `x-api-key: {admin-api-key}`

## Query Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `limit` | integer | No | Items per page (1-1000, default 20) |
| `before_id` | string | No | Cursor for previous page |
| `after_id` | string | No | Cursor for next page |
| `workspace_id` | string | No | Filter by workspace ID |
| `status` | string | No | Filter by status (`active`, `inactive`) |

## Example Request

```bash
curl -X GET "http://localhost:8080/rest/anthropic-admin-api/1.0.0/organizations/api_keys" \
  -H "anthropic-version: 2023-06-01" \
  -H "x-api-key: your-admin-api-key"
```

## Example Response

```json
{
  "data": [
    {
      "id": "apikey_01SomeApiKeyId",
      "type": "api_key",
      "name": "Production Key",
      "status": "active",
      "workspace_id": "wrkspc_01SomeWorkspaceId",
      "created_at": "2024-01-15T10:00:00Z",
      "last_used_at": "2024-11-07T05:31:56Z"
    }
  ],
  "first_id": "apikey_01SomeApiKeyId",
  "has_more": false,
  "last_id": "apikey_01SomeApiKeyId"
}
```

## Instructions

When the user asks to list or view API keys in the organization, use this operation by making a GET request to `/organizations/api_keys`. Support filtering by workspace ID or status if specified.

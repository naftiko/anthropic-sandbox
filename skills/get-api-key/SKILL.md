# Get API Key

Retrieve detailed information about a specific API key by its ID, including its name, status, and associated workspace.

## API Details

- **API**: Anthropic Administrative API
- **Method**: GET
- **Path**: `/organizations/api_keys/{api_key_id}`
- **Operation ID**: `getApiKey`
- **OpenAPI**: [anthropic-admin-api-openapi.yml](../../openapi/anthropic-admin-api-openapi.yml)

## Sandbox

Mock server URL: `http://localhost:8080/rest/anthropic-admin-api/1.0.0/organizations/api_keys/{api_key_id}`

## Required Headers

- `anthropic-version: 2023-06-01`
- `x-api-key: {admin-api-key}`

## Path Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `api_key_id` | string | Yes | Unique identifier of the API key |

## Example Request

```bash
curl -X GET "http://localhost:8080/rest/anthropic-admin-api/1.0.0/organizations/api_keys/apikey_01SomeApiKeyId" \
  -H "anthropic-version: 2023-06-01" \
  -H "x-api-key: your-admin-api-key"
```

## Example Response

```json
{
  "id": "apikey_01SomeApiKeyId",
  "type": "api_key",
  "name": "Production Key",
  "status": "active",
  "workspace_id": "wrkspc_01SomeWorkspaceId",
  "created_at": "2024-01-15T10:00:00Z",
  "last_used_at": "2024-11-07T05:31:56Z"
}
```

## Instructions

When the user asks to get or view a specific API key by ID, use this operation by making a GET request to `/organizations/api_keys/{api_key_id}`.

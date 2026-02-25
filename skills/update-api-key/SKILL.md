# Update API Key

Update the name or status of an existing API key. Can be used to activate or deactivate a key.

## API Details

- **API**: Anthropic Administrative API
- **Method**: POST
- **Path**: `/organizations/api_keys/{api_key_id}`
- **Operation ID**: `updateApiKey`
- **OpenAPI**: [anthropic-admin-api-openapi.yml](../../openapi/anthropic-admin-api-openapi.yml)

## Sandbox

Mock server URL: `http://localhost:8080/rest/anthropic-admin-api/1.0.0/organizations/api_keys/{api_key_id}`

## Required Headers

- `anthropic-version: 2023-06-01`
- `x-api-key: {admin-api-key}`
- `Content-Type: application/json`

## Path Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `api_key_id` | string | Yes | Unique identifier of the API key to update |

## Request Body

```json
{
  "name": "Updated Key Name",
  "status": "inactive"
}
```

| Field | Type | Required | Description |
|-------|------|----------|-------------|
| `name` | string | No | New name for the API key |
| `status` | string | No | New status (`active` or `inactive`) |

## Example Request

```bash
curl -X POST "http://localhost:8080/rest/anthropic-admin-api/1.0.0/organizations/api_keys/apikey_01SomeApiKeyId" \
  -H "anthropic-version: 2023-06-01" \
  -H "x-api-key: your-admin-api-key" \
  -H "Content-Type: application/json" \
  -d '{"name": "Updated Key Name", "status": "inactive"}'
```

## Example Response

```json
{
  "id": "apikey_01SomeApiKeyId",
  "type": "api_key",
  "name": "Updated Key Name",
  "status": "inactive",
  "workspace_id": "wrkspc_01SomeWorkspaceId",
  "created_at": "2024-01-15T10:00:00Z",
  "last_used_at": "2024-11-07T05:31:56Z"
}
```

## Instructions

When the user asks to update, rename, activate, or deactivate an API key, use this operation by making a POST request to `/organizations/api_keys/{api_key_id}` with the fields to update.

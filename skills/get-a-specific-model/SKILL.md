# Get A Specific Model

Retrieve information about a specific Claude model by ID or alias, including display name and creation date.

## API Details

- **API**: Anthropic Models API
- **Method**: GET
- **Path**: `/v1/models/{model_id}`
- **Operation ID**: `getModel`
- **OpenAPI**: [anthropic-models-api-openapi.yml](../../openapi/anthropic-models-api-openapi.yml)

## Sandbox

Mock server URL: `http://localhost:8080/rest/anthropic-models-api/2025-03-05/v1/models/{model_id}`

## Required Headers

- `anthropic-version: 2023-06-01`
- `x-api-key: {api-key}`

## Path Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `model_id` | string | Yes | Model identifier or alias (e.g., `claude-sonnet-4-20250514`) |

## Example Request

```bash
curl -X GET "http://localhost:8080/rest/anthropic-models-api/2025-03-05/v1/models/claude-sonnet-4-20250514" \
  -H "anthropic-version: 2023-06-01" \
  -H "x-api-key: your-api-key"
```

## Example Response

```json
{
  "id": "claude-sonnet-4-20250514",
  "type": "model",
  "display_name": "Claude Sonnet 4",
  "created_at": "2025-05-14T00:00:00Z"
}
```

## Instructions

When the user asks to get information about a specific model or resolve a model alias, use this operation by making a GET request to `/v1/models/{model_id}`. Can be used to verify a model ID is valid and get its canonical identifier.

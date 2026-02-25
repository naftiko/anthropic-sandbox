# List Available Models

List all available Claude models accessible via the API. More recently released models are listed first.

## API Details

- **API**: Anthropic Models API
- **Method**: GET
- **Path**: `/v1/models`
- **Operation ID**: `listModels`
- **OpenAPI**: [anthropic-models-api-openapi.yml](../../openapi/anthropic-models-api-openapi.yml)

## Sandbox

Mock server URL: `http://localhost:8080/rest/anthropic-models-api/2025-03-05/v1/models`

## Required Headers

- `anthropic-version: 2023-06-01`
- `x-api-key: {api-key}`

## Query Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `limit` | integer | No | Items per page (1-1000, default 20) |
| `before_id` | string | No | Cursor for previous page |
| `after_id` | string | No | Cursor for next page |

## Example Request

```bash
curl -X GET "http://localhost:8080/rest/anthropic-models-api/2025-03-05/v1/models" \
  -H "anthropic-version: 2023-06-01" \
  -H "x-api-key: your-api-key"
```

## Example Response

```json
{
  "data": [
    {
      "id": "claude-sonnet-4-20250514",
      "type": "model",
      "display_name": "Claude Sonnet 4",
      "created_at": "2025-05-14T00:00:00Z"
    },
    {
      "id": "claude-3-5-sonnet-20241022",
      "type": "model",
      "display_name": "Claude 3.5 Sonnet",
      "created_at": "2024-10-22T00:00:00Z"
    }
  ],
  "first_id": "claude-sonnet-4-20250514",
  "has_more": true,
  "last_id": "claude-3-haiku-20240307"
}
```

## Instructions

When the user asks to list available models or discover what Claude models they can use, use this operation by making a GET request to `/v1/models`. Return the list of model IDs and display names.

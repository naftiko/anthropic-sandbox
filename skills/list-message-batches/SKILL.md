# List Message Batches

Retrieve a paginated list of all message batches associated with your account.

## API Details

- **API**: Anthropic Message Batches API
- **Method**: GET
- **Path**: `/messages/batches`
- **Operation ID**: `listMessageBatches`
- **OpenAPI**: [anthropic-message-batches-api-openapi.yml](../../openapi/anthropic-message-batches-api-openapi.yml)

## Sandbox

Mock server URL: `http://localhost:8080/rest/anthropic-message-batches-api/1.0.0/messages/batches`

## Required Headers

- `anthropic-version: 2023-06-01`
- `x-api-key: {api-key}`

## Optional Headers

- `anthropic-beta: message-batches-2024-09-24`

## Query Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `limit` | integer | No | Items per page (1-1000, default 20) |
| `before_id` | string | No | Cursor for previous page |
| `after_id` | string | No | Cursor for next page |

## Example Request

```bash
curl -X GET "http://localhost:8080/rest/anthropic-message-batches-api/1.0.0/messages/batches" \
  -H "anthropic-version: 2023-06-01" \
  -H "x-api-key: your-api-key"
```

## Example Response

```json
{
  "data": [
    {
      "id": "msgbatch_013Zva2CMHLNnXjNJJKqJ2EF",
      "type": "message_batch",
      "processing_status": "ended",
      "request_counts": {
        "processing": 0,
        "succeeded": 150,
        "errored": 0,
        "canceled": 0,
        "expired": 0
      },
      "created_at": "2024-08-20T18:37:24Z",
      "expires_at": "2024-08-21T18:37:24Z",
      "results_url": "https://api.anthropic.com/v1/messages/batches/msgbatch_013Zva2CMHLNnXjNJJKqJ2EF/results"
    }
  ],
  "first_id": "msgbatch_013Zva2CMHLNnXjNJJKqJ2EF",
  "has_more": true,
  "last_id": "msgbatch_024Abw3DNIMOoYkKKLRrK3FG"
}
```

## Instructions

When the user asks to list or view message batches, use this operation by making a GET request to `/messages/batches`. Support pagination using cursor parameters.

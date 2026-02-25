# Create Message Batch

Submit a batch of up to 10,000 message creation requests for asynchronous background processing. Ideal for high-volume, non-time-sensitive workloads at reduced cost.

## API Details

- **API**: Anthropic Message Batches API
- **Method**: POST
- **Path**: `/messages/batches`
- **Operation ID**: `createMessageBatch`
- **OpenAPI**: [anthropic-message-batches-api-openapi.yml](../../openapi/anthropic-message-batches-api-openapi.yml)

## Sandbox

Mock server URL: `http://localhost:8080/rest/anthropic-message-batches-api/1.0.0/messages/batches`

## Required Headers

- `anthropic-version: 2023-06-01`
- `x-api-key: {api-key}`
- `Content-Type: application/json`

## Request Body

```json
{
  "requests": [
    {
      "custom_id": "request-001",
      "params": {
        "model": "claude-sonnet-4-20250514",
        "max_tokens": 1024,
        "messages": [
          {
            "role": "user",
            "content": "Hello, what is the capital of France?"
          }
        ]
      }
    }
  ]
}
```

| Field | Type | Required | Description |
|-------|------|----------|-------------|
| `requests` | array | Yes | Array of 1-10,000 message requests |
| `requests[].custom_id` | string | Yes | Developer-provided unique ID for matching results |
| `requests[].params` | object | Yes | Message creation parameters |
| `requests[].params.model` | string | Yes | Claude model to use |
| `requests[].params.max_tokens` | integer | Yes | Maximum tokens to generate |
| `requests[].params.messages` | array | Yes | Conversation messages |

## Example Request

```bash
curl -X POST "http://localhost:8080/rest/anthropic-message-batches-api/1.0.0/messages/batches" \
  -H "anthropic-version: 2023-06-01" \
  -H "x-api-key: your-api-key" \
  -H "Content-Type: application/json" \
  -d '{"requests": [{"custom_id": "req-1", "params": {"model": "claude-sonnet-4-20250514", "max_tokens": 1024, "messages": [{"role": "user", "content": "Hello!"}]}}]}'
```

## Example Response

```json
{
  "id": "msgbatch_013Zva2CMHLNnXjNJJKqJ2EF",
  "type": "message_batch",
  "processing_status": "in_progress",
  "request_counts": {
    "processing": 100,
    "succeeded": 0,
    "errored": 0,
    "canceled": 0,
    "expired": 0
  },
  "created_at": "2024-08-20T18:37:24Z",
  "expires_at": "2024-08-21T18:37:24Z",
  "results_url": null
}
```

## Instructions

When the user asks to create a message batch or submit bulk messages, use this operation by making a POST request to `/messages/batches`. Ensure each request in the batch has a unique `custom_id` for result matching. Batches process within 24 hours.

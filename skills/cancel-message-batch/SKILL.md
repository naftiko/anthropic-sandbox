# Cancel Message Batch

Initiate cancellation of a Message Batch that is currently being processed. The batch enters a `canceling` state and any in-progress, non-interruptible requests may still complete.

## API Details

- **API**: Anthropic Message Batches API
- **Method**: POST
- **Path**: `/messages/batches/{message_batch_id}/cancel`
- **Operation ID**: `cancelMessageBatch`
- **OpenAPI**: [anthropic-message-batches-api-openapi.yml](../../openapi/anthropic-message-batches-api-openapi.yml)

## Sandbox

Mock server URL: `http://localhost:8080/rest/anthropic-message-batches-api/1.0.0/messages/batches/{message_batch_id}/cancel`

## Required Headers

- `anthropic-version: 2023-06-01`
- `x-api-key: {api-key}`

## Path Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `message_batch_id` | string | Yes | Unique identifier of the message batch to cancel |

## Example Request

```bash
curl -X POST "http://localhost:8080/rest/anthropic-message-batches-api/1.0.0/messages/batches/msgbatch_013Zva2CMHLNnXjNJJKqJ2EF/cancel" \
  -H "anthropic-version: 2023-06-01" \
  -H "x-api-key: your-api-key"
```

## Example Response

```json
{
  "id": "msgbatch_013Zva2CMHLNnXjNJJKqJ2EF",
  "type": "message_batch",
  "processing_status": "canceling",
  "request_counts": {
    "processing": 50,
    "succeeded": 40,
    "errored": 5,
    "canceled": 5,
    "expired": 0
  },
  "created_at": "2024-08-20T18:37:24Z",
  "cancel_initiated_at": "2024-08-20T19:00:00Z"
}
```

## Instructions

When the user asks to cancel or stop a message batch, use this operation by making a POST request to `/messages/batches/{message_batch_id}/cancel`. Note that cancellation is not immediate — the batch enters `canceling` status and some requests may still complete.

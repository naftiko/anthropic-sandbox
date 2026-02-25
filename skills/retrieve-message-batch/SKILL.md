# Retrieve Message Batch

Get the current status and details of a previously created message batch processing job.

## API Details

- **API**: Anthropic Message Batches API
- **Method**: GET
- **Path**: `/messages/batches/{message_batch_id}`
- **Operation ID**: `retrieveMessageBatch`
- **OpenAPI**: [anthropic-message-batches-api-openapi.yml](../../openapi/anthropic-message-batches-api-openapi.yml)

## Sandbox

Mock server URL: `http://localhost:8080/rest/anthropic-message-batches-api/1.0.0/messages/batches/{message_batch_id}`

## Required Headers

- `anthropic-version: 2023-06-01`
- `x-api-key: {api-key}`

## Path Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `message_batch_id` | string | Yes | Unique identifier of the message batch |

## Processing Status Values

| Status | Description |
|--------|-------------|
| `in_progress` | Batch is actively being processed |
| `canceling` | Cancellation has been initiated |
| `ended` | Processing has completed (check results) |

## Example Request

```bash
curl -X GET "http://localhost:8080/rest/anthropic-message-batches-api/1.0.0/messages/batches/msgbatch_013Zva2CMHLNnXjNJJKqJ2EF" \
  -H "anthropic-version: 2023-06-01" \
  -H "x-api-key: your-api-key"
```

## Example Response

```json
{
  "id": "msgbatch_013Zva2CMHLNnXjNJJKqJ2EF",
  "type": "message_batch",
  "processing_status": "in_progress",
  "request_counts": {
    "processing": 100,
    "succeeded": 50,
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

When the user asks to check the status of a message batch, use this operation by making a GET request to `/messages/batches/{message_batch_id}`. Poll this endpoint to check when `processing_status` becomes `ended` before retrieving results.

# Delete Message Batch

Permanently remove a message batch from your account. This action cannot be undone.

## API Details

- **API**: Anthropic Message Batches API
- **Method**: DELETE
- **Path**: `/messages/batches/{message_batch_id}`
- **Operation ID**: `deleteMessageBatch`
- **OpenAPI**: [anthropic-message-batches-api-openapi.yml](../../openapi/anthropic-message-batches-api-openapi.yml)

## Sandbox

Mock server URL: `http://localhost:8080/rest/anthropic-message-batches-api/1.0.0/messages/batches/{message_batch_id}`

## Required Headers

- `anthropic-version: 2023-06-01`
- `x-api-key: {api-key}`

## Path Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `message_batch_id` | string | Yes | Unique identifier of the message batch to delete |

## Example Request

```bash
curl -X DELETE "http://localhost:8080/rest/anthropic-message-batches-api/1.0.0/messages/batches/msgbatch_013Zva2CMHLNnXjNJJKqJ2EF" \
  -H "anthropic-version: 2023-06-01" \
  -H "x-api-key: your-api-key"
```

## Example Response

```json
{
  "id": "msgbatch_013Zva2CMHLNnXjNJJKqJ2EF",
  "type": "message_batch_deleted"
}
```

## Instructions

When the user asks to delete a message batch, use this operation by making a DELETE request to `/messages/batches/{message_batch_id}`. This permanently removes the batch and all associated results.

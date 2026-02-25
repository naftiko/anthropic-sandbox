# Retrieve Message Batch Results

Stream the results of a completed Message Batch as a JSONL file. Each line contains the result for a single request, matched via the `custom_id` field.

## API Details

- **API**: Anthropic Message Batches API
- **Method**: GET
- **Path**: `/messages/batches/{message_batch_id}/results`
- **Operation ID**: `retrieveMessageBatchResults`
- **OpenAPI**: [anthropic-message-batches-api-openapi.yml](../../openapi/anthropic-message-batches-api-openapi.yml)

## Sandbox

Mock server URL: `http://localhost:8080/rest/anthropic-message-batches-api/1.0.0/messages/batches/{message_batch_id}/results`

## Required Headers

- `anthropic-version: 2023-06-01`
- `x-api-key: {api-key}`

## Path Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `message_batch_id` | string | Yes | Unique identifier of the completed message batch |

## Response Format

Returns `application/x-jsonl` (newline-delimited JSON). Each line is a JSON object with:
- `custom_id`: matches the ID from the original request
- `result.type`: `succeeded`, `errored`, `canceled`, or `expired`
- `result.message`: (for `succeeded`) the full message response

## Example Request

```bash
curl -X GET "http://localhost:8080/rest/anthropic-message-batches-api/1.0.0/messages/batches/msgbatch_013Zva2CMHLNnXjNJJKqJ2EF/results" \
  -H "anthropic-version: 2023-06-01" \
  -H "x-api-key: your-api-key" \
  --output results.jsonl
```

## Example Response (JSONL)

```jsonl
{"custom_id":"request-001","result":{"type":"succeeded","message":{"id":"msg_01FqfsLoHwgeFbguDgpz48m7","type":"message","role":"assistant","model":"claude-sonnet-4-20250514","content":[{"type":"text","text":"The capital of France is Paris."}],"stop_reason":"end_turn","usage":{"input_tokens":15,"output_tokens":8}}}}
{"custom_id":"request-002","result":{"type":"succeeded","message":{"id":"msg_02GrsrtMhxghGfchvEhq59n8","type":"message","role":"assistant","model":"claude-sonnet-4-20250514","content":[{"type":"text","text":"Quantum computing uses quantum bits..."}],"stop_reason":"end_turn","usage":{"input_tokens":12,"output_tokens":35}}}}
```

## Instructions

When the user asks to get or retrieve results from a message batch, use this operation. Only call this after confirming the batch `processing_status` is `ended` via the Retrieve Message Batch operation. Parse each line of the JSONL response as a separate JSON object and match results to original requests using `custom_id`.

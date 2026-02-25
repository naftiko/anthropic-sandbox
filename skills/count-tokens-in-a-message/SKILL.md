# Count Tokens In A Message

Count the number of tokens that would be consumed by a message before sending it, enabling informed decisions about message length and token budget management.

## API Details

- **API**: Anthropic Messages API
- **Method**: POST
- **Path**: `/v1/messages/count_tokens`
- **Operation ID**: `countTokens`
- **OpenAPI**: [anthropic-messages-api-openapi.yml](../../openapi/anthropic-messages-api-openapi.yml)

## Sandbox

Mock server URL: `http://localhost:8080/rest/anthropic-models-api/2025-03-05/v1/messages/count_tokens`

## Required Headers

- `anthropic-version: 2023-06-01`
- `x-api-key: {api-key}`
- `Content-Type: application/json`

## Request Body

```json
{
  "model": "claude-sonnet-4-20250514",
  "messages": [
    {
      "role": "user",
      "content": "Hello, how are you?"
    }
  ]
}
```

| Field | Type | Required | Description |
|-------|------|----------|-------------|
| `model` | string | Yes | The Claude model to use for token counting |
| `messages` | array | Yes | Messages to count tokens for |
| `system` | string/array | No | System prompt to include in count |
| `tools` | array | No | Tool definitions to include in count |
| `thinking` | object | No | Thinking configuration to include in count |

## Example Request

```bash
curl -X POST "http://localhost:8080/rest/anthropic-models-api/2025-03-05/v1/messages/count_tokens" \
  -H "anthropic-version: 2023-06-01" \
  -H "x-api-key: your-api-key" \
  -H "Content-Type: application/json" \
  -d '{"model": "claude-sonnet-4-20250514", "messages": [{"role": "user", "content": "Hello, how are you?"}]}'
```

## Example Response

```json
{
  "input_tokens": 2095
}
```

## Instructions

When the user asks to count tokens in a message or wants to know the token cost before sending, use this operation by making a POST request to `/v1/messages/count_tokens` with the same parameters you would use for a message creation request (without actually sending it).

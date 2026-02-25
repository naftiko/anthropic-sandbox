# Create A Message

Send a structured list of input messages to a Claude model and receive a generated response. The primary interface for interacting with Claude for conversations and content generation.

## API Details

- **API**: Anthropic Messages API
- **Method**: POST
- **Path**: `/v1/messages`
- **Operation ID**: `createMessage`
- **OpenAPI**: [anthropic-messages-api-openapi.yml](../../openapi/anthropic-messages-api-openapi.yml)

## Sandbox

Mock server URL: `http://localhost:8080/rest/anthropic-models-api/2025-03-05/v1/messages`

## Required Headers

- `anthropic-version: 2023-06-01`
- `x-api-key: {api-key}`
- `Content-Type: application/json`

## Request Body

```json
{
  "model": "claude-sonnet-4-20250514",
  "max_tokens": 1024,
  "messages": [
    {
      "role": "user",
      "content": "Hello, Claude! How are you today?"
    }
  ]
}
```

| Field | Type | Required | Description |
|-------|------|----------|-------------|
| `model` | string | Yes | The Claude model to use |
| `max_tokens` | integer | Yes | Maximum tokens in the response (min 1) |
| `messages` | array | Yes | Conversation messages (up to 100,000) |
| `system` | string/array | No | System prompt for context and instructions |
| `temperature` | number | No | Randomness (0.0-1.0, default 1.0) |
| `tools` | array | No | Tool definitions for function calling |
| `stream` | boolean | No | Enable streaming with server-sent events |
| `thinking` | object | No | Enable extended thinking |

## Example Request

```bash
curl -X POST "http://localhost:8080/rest/anthropic-models-api/2025-03-05/v1/messages" \
  -H "anthropic-version: 2023-06-01" \
  -H "x-api-key: your-api-key" \
  -H "Content-Type: application/json" \
  -d '{"model": "claude-sonnet-4-20250514", "max_tokens": 1024, "messages": [{"role": "user", "content": "Hello!"}]}'
```

## Example Response

```json
{
  "id": "msg_013Zva2CMHLNnXjNJJKqJ2EF",
  "type": "message",
  "role": "assistant",
  "content": [
    {
      "type": "text",
      "text": "Hi! My name is Claude. I'm doing well, thank you for asking! How can I help you today?"
    }
  ],
  "model": "claude-sonnet-4-20250514",
  "stop_reason": "end_turn",
  "stop_sequence": null,
  "usage": {
    "input_tokens": 12,
    "output_tokens": 25
  }
}
```

## Instructions

When the user asks to send a message to Claude, generate text, have a conversation, or use Claude for any content generation task, use this operation by making a POST request to `/v1/messages`. Specify the model, max_tokens, and messages array. Optionally include a system prompt to guide Claude's behavior.

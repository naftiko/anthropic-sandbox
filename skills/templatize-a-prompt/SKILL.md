# Templatize A Prompt

Convert a prompt with specific values into a reusable template by identifying and extracting variables. Concrete values are replaced with uppercase variable placeholders. Part of the closed research preview Prompt Tools API.

## API Details

- **API**: Anthropic Prompt Tools API
- **Method**: POST
- **Path**: `/v1/experimental/templatize_prompt`
- **Operation ID**: `templatizePrompt`
- **OpenAPI**: [anthropic-prompts-api-openapi.yml](../../openapi/anthropic-prompts-api-openapi.yml)

## Sandbox

Mock server URL: `http://localhost:8080/rest/anthropic-prompt-tools-api/1.0.0/v1/experimental/templatize_prompt`

## Required Headers

- `anthropic-version: 2023-06-01`
- `anthropic-beta: prompt-tools-2025-04-02`
- `x-api-key: {api-key}`
- `Content-Type: application/json`

## Requirements

- Must have joined the closed research preview for prompt tools APIs
- Messages must contain only text-only content blocks
- No tool calls, images, or prompt caching blocks allowed

## Request Body

```json
{
  "messages": [
    {
      "role": "user",
      "content": [
        {
          "type": "text",
          "text": "Translate hello to German"
        }
      ]
    }
  ],
  "system": "You are a professional English to German translator"
}
```

| Field | Type | Required | Description |
|-------|------|----------|-------------|
| `messages` | array | Yes | The prompt to templatize |
| `system` | string | No | System prompt to also templatize |

## Example Request

```bash
curl -X POST "http://localhost:8080/rest/anthropic-prompt-tools-api/1.0.0/v1/experimental/templatize_prompt" \
  -H "anthropic-version: 2023-06-01" \
  -H "anthropic-beta: prompt-tools-2025-04-02" \
  -H "x-api-key: your-api-key" \
  -H "Content-Type: application/json" \
  -d '{"messages": [{"role": "user", "content": [{"type": "text", "text": "Translate hello to German"}]}]}'
```

## Example Response

```json
{
  "messages": [
    {
      "role": "user",
      "content": [
        {
          "type": "text",
          "text": "Translate {{WORD_TO_TRANSLATE}} to {{TARGET_LANGUAGE}}"
        }
      ]
    }
  ],
  "system": "You are a professional English to {{TARGET_LANGUAGE}} translator",
  "usage": {
    "input_tokens": 15,
    "output_tokens": 25
  },
  "variable_values": {
    "WORD_TO_TRANSLATE": "hello",
    "TARGET_LANGUAGE": "German"
  }
}
```

## Instructions

When the user asks to templatize, parameterize, or make a prompt reusable, use this operation by making a POST request to `/v1/experimental/templatize_prompt`. The `variable_values` in the response shows what was extracted, and the returned messages contain the template with `{{VARIABLE_NAME}}` placeholders.

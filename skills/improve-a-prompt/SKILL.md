# Improve A Prompt

Enhance an existing prompt based on specific feedback or general prompt engineering best practices. Part of the closed research preview Prompt Tools API.

## API Details

- **API**: Anthropic Prompt Tools API
- **Method**: POST
- **Path**: `/v1/experimental/improve_prompt`
- **Operation ID**: `improvePrompt`
- **OpenAPI**: [anthropic-prompts-api-openapi.yml](../../openapi/anthropic-prompts-api-openapi.yml)

## Sandbox

Mock server URL: `http://localhost:8080/rest/anthropic-prompt-tools-api/1.0.0/v1/experimental/improve_prompt`

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
          "text": "Concise recipe for {{food}}"
        }
      ]
    }
  ],
  "feedback": "Make the recipes shorter and more actionable",
  "system": "You are a professional meal prep chef",
  "target_model": "claude-sonnet-4-20250514"
}
```

| Field | Type | Required | Description |
|-------|------|----------|-------------|
| `messages` | array | Yes | The existing prompt to improve |
| `feedback` | string | No | Specific guidance for improvements |
| `system` | string | No | Existing system prompt to incorporate |
| `target_model` | string | No | Target model for the improved prompt |

## Example Request

```bash
curl -X POST "http://localhost:8080/rest/anthropic-prompt-tools-api/1.0.0/v1/experimental/improve_prompt" \
  -H "anthropic-version: 2023-06-01" \
  -H "anthropic-beta: prompt-tools-2025-04-02" \
  -H "x-api-key: your-api-key" \
  -H "Content-Type: application/json" \
  -d '{"messages": [{"role": "user", "content": [{"type": "text", "text": "Write a summary"}]}], "feedback": "Make it more detailed"}'
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
          "text": "You are a professional meal prep chef. Create a detailed recipe for {{food}} including preparation time, cooking time, and step-by-step instructions."
        }
      ]
    }
  ],
  "system": "",
  "usage": {
    "input_tokens": 45,
    "output_tokens": 180
  }
}
```

## Instructions

When the user asks to improve, enhance, or refine an existing prompt, use this operation by making a POST request to `/v1/experimental/improve_prompt` with the current prompt messages and optional feedback.

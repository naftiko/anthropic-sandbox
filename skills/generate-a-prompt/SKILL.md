# Generate A Prompt

Generate a well-written, production-ready prompt for a specified task using Anthropic's prompt engineering expertise. Part of the closed research preview Prompt Tools API.

## API Details

- **API**: Anthropic Prompt Tools API
- **Method**: POST
- **Path**: `/v1/experimental/generate_prompt`
- **Operation ID**: `generatePrompt`
- **OpenAPI**: [anthropic-prompts-api-openapi.yml](../../openapi/anthropic-prompts-api-openapi.yml)

## Sandbox

Mock server URL: `http://localhost:8080/rest/anthropic-prompt-tools-api/1.0.0/v1/experimental/generate_prompt`

## Required Headers

- `anthropic-version: 2023-06-01`
- `anthropic-beta: prompt-tools-2025-04-02`
- `x-api-key: {api-key}`
- `Content-Type: application/json`

## Requirements

- Must have joined the closed research preview for prompt tools APIs
- Must use the API directly (not available in SDK)

## Request Body

```json
{
  "task": "a chef for a meal prep planning service",
  "target_model": "claude-sonnet-4-20250514"
}
```

| Field | Type | Required | Description |
|-------|------|----------|-------------|
| `task` | string | Yes | Description of what the prompt should do or the role it should define |
| `target_model` | string | No | The model this prompt will be used with |

## Example Request

```bash
curl -X POST "http://localhost:8080/rest/anthropic-prompt-tools-api/1.0.0/v1/experimental/generate_prompt" \
  -H "anthropic-version: 2023-06-01" \
  -H "anthropic-beta: prompt-tools-2025-04-02" \
  -H "x-api-key: your-api-key" \
  -H "Content-Type: application/json" \
  -d '{"task": "a helpful customer service agent for a software company"}'
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
          "text": "You are a chef for a meal prep planning service. Your role is to help users plan their weekly meals, create shopping lists, and provide cooking instructions."
        }
      ]
    },
    {
      "role": "assistant",
      "content": [
        {
          "type": "text",
          "text": "<recipe_planning>"
        }
      ]
    }
  ],
  "system": "",
  "usage": {
    "input_tokens": 25,
    "output_tokens": 150
  }
}
```

## Instructions

When the user asks to generate a new prompt for a specific task or role, use this operation by making a POST request to `/v1/experimental/generate_prompt` with a clear task description. The generated messages array can be used directly with the Messages API.

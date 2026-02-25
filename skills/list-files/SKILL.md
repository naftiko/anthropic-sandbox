# List Files

Retrieve a paginated list of all files that have been uploaded to the organization via the Files API.

## API Details

- **API**: Anthropic Files API
- **Method**: GET
- **Path**: `/files`
- **Operation ID**: `listFiles`
- **OpenAPI**: [anthropic-files-api-openapi.yml](../../openapi/anthropic-files-api-openapi.yml)

## Sandbox

Mock server URL: `http://localhost:8080/rest/anthropic-files-api/1.0.0/files`

## Required Headers

- `anthropic-version: 2023-06-01`
- `anthropic-beta: files-api-2025-04-14`
- `x-api-key: {api-key}`

## Query Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `limit` | integer | No | Items per page (1-1000, default 20) |
| `before_id` | string | No | Cursor for previous page |
| `after_id` | string | No | Cursor for next page |

## Example Request

```bash
curl -X GET "http://localhost:8080/rest/anthropic-files-api/1.0.0/files" \
  -H "anthropic-version: 2023-06-01" \
  -H "anthropic-beta: files-api-2025-04-14" \
  -H "x-api-key: your-api-key"
```

## Example Response

```json
{
  "data": [
    {
      "id": "file_011CNha8iCJcU1wXNR6q4V8w",
      "type": "file",
      "filename": "quarterly-report.pdf",
      "mime_type": "application/pdf",
      "size_bytes": 2048576,
      "created_at": "2024-11-07T05:31:56Z",
      "downloadable": true
    }
  ],
  "first_id": "file_011CNha8iCJcU1wXNR6q4V8w",
  "has_more": true,
  "last_id": "file_033EPjc0kELeW3zZPT8s6X0y"
}
```

## Instructions

When the user asks to list or view uploaded files, use this operation by making a GET request to `/files` with the required `anthropic-beta: files-api-2025-04-14` header.

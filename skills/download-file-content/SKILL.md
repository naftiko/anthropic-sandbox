# Download File Content

Download the actual binary content of a previously uploaded file.

## API Details

- **API**: Anthropic Files API
- **Method**: GET
- **Path**: `/files/{file_id}/content`
- **Operation ID**: `downloadFileContent`
- **OpenAPI**: [anthropic-files-api-openapi.yml](../../openapi/anthropic-files-api-openapi.yml)

## Sandbox

Mock server URL: `http://localhost:8080/rest/anthropic-files-api/1.0.0/files/{file_id}/content`

## Required Headers

- `anthropic-version: 2023-06-01`
- `anthropic-beta: files-api-2025-04-14`
- `x-api-key: {api-key}`

## Path Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `file_id` | string | Yes | Unique identifier of the file to download |

## Example Request

```bash
curl -X GET "http://localhost:8080/rest/anthropic-files-api/1.0.0/files/file_011CNha8iCJcU1wXNR6q4V8w/content" \
  -H "anthropic-version: 2023-06-01" \
  -H "anthropic-beta: files-api-2025-04-14" \
  -H "x-api-key: your-api-key" \
  --output downloaded-file.pdf
```

## Response

Returns binary content (`application/octet-stream`) of the file. The `downloadable` field in the file metadata must be `true` for this operation to succeed.

## Instructions

When the user asks to download or retrieve the content of a file, use this operation by making a GET request to `/files/{file_id}/content`. Only files with `downloadable: true` can be downloaded. Save the binary response to a local file.

# Get File Metadata

Retrieve metadata information for a previously uploaded file, including filename, MIME type, size, and download availability.

## API Details

- **API**: Anthropic Files API
- **Method**: GET
- **Path**: `/files/{file_id}`
- **Operation ID**: `getFileMetadata`
- **OpenAPI**: [anthropic-files-api-openapi.yml](../../openapi/anthropic-files-api-openapi.yml)

## Sandbox

Mock server URL: `http://localhost:8080/rest/anthropic-files-api/1.0.0/files/{file_id}`

## Required Headers

- `anthropic-version: 2023-06-01`
- `anthropic-beta: files-api-2025-04-14`
- `x-api-key: {api-key}`

## Path Parameters

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `file_id` | string | Yes | Unique identifier of the file |

## Example Request

```bash
curl -X GET "http://localhost:8080/rest/anthropic-files-api/1.0.0/files/file_011CNha8iCJcU1wXNR6q4V8w" \
  -H "anthropic-version: 2023-06-01" \
  -H "anthropic-beta: files-api-2025-04-14" \
  -H "x-api-key: your-api-key"
```

## Example Response

```json
{
  "id": "file_011CNha8iCJcU1wXNR6q4V8w",
  "type": "file",
  "filename": "quarterly-report.pdf",
  "mime_type": "application/pdf",
  "size_bytes": 2048576,
  "created_at": "2024-11-07T05:31:56Z",
  "downloadable": true
}
```

## Instructions

When the user asks to get metadata or information about a specific file, use this operation by making a GET request to `/files/{file_id}`. Include the `anthropic-beta: files-api-2025-04-14` header.

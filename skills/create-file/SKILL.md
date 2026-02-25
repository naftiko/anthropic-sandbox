# Create File

Upload a file to Anthropic's servers for use in subsequent API calls such as message creation and batch processing.

## API Details

- **API**: Anthropic Files API
- **Method**: POST
- **Path**: `/files`
- **Operation ID**: `createFile`
- **OpenAPI**: [anthropic-files-api-openapi.yml](../../openapi/anthropic-files-api-openapi.yml)

## Sandbox

Mock server URL: `http://localhost:8080/rest/anthropic-files-api/1.0.0/files`

## Required Headers

- `anthropic-version: 2023-06-01`
- `anthropic-beta: files-api-2025-04-14`
- `x-api-key: {api-key}`
- `Content-Type: multipart/form-data`

## Supported File Types

- `application/pdf`
- `image/jpeg`, `image/png`, `image/gif`, `image/webp`
- `text/plain`, `text/csv`
- `application/json`
- `application/vnd.openxmlformats-officedocument.wordprocessingml.document` (DOCX)
- `application/vnd.openxmlformats-officedocument.spreadsheetml.sheet` (XLSX)

## Example Request

```bash
curl -X POST "http://localhost:8080/rest/anthropic-files-api/1.0.0/files" \
  -H "anthropic-version: 2023-06-01" \
  -H "anthropic-beta: files-api-2025-04-14" \
  -H "x-api-key: your-api-key" \
  -F "file=@/path/to/document.pdf"
```

## Example Response

```json
{
  "id": "file_011CNha8iCJcU1wXNR6q4V8w",
  "type": "file",
  "filename": "document.pdf",
  "mime_type": "application/pdf",
  "size_bytes": 2048576,
  "created_at": "2024-11-07T05:31:56Z",
  "downloadable": true
}
```

## Instructions

When the user asks to upload a file to Anthropic, use this operation by making a multipart POST request to `/files` with the file as form data. Include the `anthropic-beta: files-api-2025-04-14` header. Return the file ID for use in future API calls.

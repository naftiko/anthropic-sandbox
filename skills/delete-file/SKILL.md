# Delete File

Permanently delete a file from Anthropic's storage system. This action cannot be undone.

## API Details

- **API**: Anthropic Files API
- **Method**: DELETE
- **Path**: `/files/{file_id}`
- **Operation ID**: `deleteFile`
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
| `file_id` | string | Yes | Unique identifier of the file to delete |

## Example Request

```bash
curl -X DELETE "http://localhost:8080/rest/anthropic-files-api/1.0.0/files/file_011CNha8iCJcU1wXNR6q4V8w" \
  -H "anthropic-version: 2023-06-01" \
  -H "anthropic-beta: files-api-2025-04-14" \
  -H "x-api-key: your-api-key"
```

## Example Response

```json
{
  "id": "file_011CNha8iCJcU1wXNR6q4V8w",
  "type": "file_deleted"
}
```

## Instructions

When the user asks to delete a file, use this operation by making a DELETE request to `/files/{file_id}`. Include the `anthropic-beta: files-api-2025-04-14` header. This operation is irreversible.

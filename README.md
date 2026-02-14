# Anthropic API & MCP Sandbox
This is an API sandbox for the Anthropic API & MCP Sandbox, using an OpenAPI specification with examples, Microcks and Bruno as the sandbox interface, and this GitHub repository as the vehicle for delivering a localized sandbox.

## APIs.json
There is an APIs.yml file in the root of this repository, providing an index of all the artifacts used as part of this API sandbox, providing a machine-readable way to read, manage, and execute the sandbox available here.

## OpenAPI
This sandbox uses OpenAPI as the definition, providing [a complete definition of all available paths for the Anthropic API & MCP Sandbox. The OpenAPI for this sandnbox uses examples and Microcks extensions to mock the requests and responses for each API operation, something we will iterate and expand upon with richer examples as we move forward.

## Microcks
This sandbox uses Microcks to deliver the mock API. [You just install Microcks, with the Docker extension being the easiest](https://microcks.io/documentation/guides/installation/docker-desktop-extension/), [import the OpenAPI as a service](openapi/notion-openapi.yml), and you have a mocked API for all APIs, available via REST and MCP APIs--providing a multi-protocol sandbox.

## Bruno
This sandbox [uses Bruno as the client](https://www.usebruno.com/), leveraging Bruno Collections pre-generated from the OpenAPI and Bruno environments that uses the localhost and port of Microcks to work with the mocked API. You just have to install Microcks, then open the collection provided in this repository, select the available environment, and begin calling the Anthropic API & MCP Sandbox via the sandbox.

## Summary
This is a summary of this sandbox, breaking down the available paths, operations, and other relevant detail regarding the scope of this sandbox, designed to support development and testing against the Anthropic API & MCP Sandbox.

- Number of Paths: 29
- Number of Operations: 43
- Number of Read Operations: 19
- Number of Write Operations: 24
- Number of Schemas: 106
- Number of Responses: 3
- Number of Parameters: 39
- Number of Examples: 76
- Number of Request Bodies: 0
- Number of Headers: 7

## OpenAPIs
These are the OpenAPIs available for the Anthropic API & MCP Sandbox, which are made available via this sandbox API, which can be imported into Microcks and deployed as a sandbox using their mock feature.

  - [Anthropic Admin API](openapi/anthropic-admin-api-openapi.yml)
  - [Anthropic Files API](openapi/anthropic-files-api-openapi.yml)
  - [Anthropic Message Batches API](openapi/anthropic-message-batches-api-openapi.yml)
  - [Anthropic Prompt Tools API](openapi/anthropic-messages-api-openapi.yml)
  - [Anthropic Models API](openapi/anthropic-models-api-openapi.yml)
  - [Anthropic Prompt Tools API](openapi/anthropic-prompts-api-openapi.yml)

## Resources
These are the resources available via the Anthropic API & MCP Sandbox, which are made available via this sandbox API, which are applied as tags to each operation in the OpenAPI.

  - Api Keys
  - Files
  - Message Batches
  - Messages
  - Models
  - Organization
  - Organization Invites
  - Organization Members
  - Prompt Generation
  - Prompt Improvement
  - Prompt Templatization
  - Tokens
  - Workspace Members
  - Workspaces

## Operations
These are all of the available operations in this sandbox, providing a complete view of what you can do within this sandbox using the mocked Anthropic API & MCP Sandbox.

  - Add Workspace Member
  - Archive Workspace
  - Cancel Message Batch
  - Count Tokens In A Message
  - Create A Message
  - Create File
  - Create Message Batch
  - Create Organization Invite
  - Create Workspace
  - Delete File
  - Delete Message Batch
  - Delete Organization Invite
  - Download File Content
  - Generate A Prompt
  - Generate A Prompt
  - Get A Specific Model
  - Get Api Key
  - Get Current Organization
  - Get File Metadata
  - Get Organization Invite
  - Get Organization Member
  - Get Workspace
  - Get Workspace Member
  - Improve A Prompt
  - Improve A Prompt
  - List Api Keys
  - List Available Models
  - List Files
  - List Message Batches
  - List Organization Invites
  - List Organization Members
  - List Workspace Members
  - List Workspaces
  - Remove Organization Member
  - Remove Workspace Member
  - Retrieve Message Batch
  - Retrieve Message Batch Results
  - Templatize A Prompt
  - Templatize A Prompt
  - Update Api Key
  - Update Organization Member
  - Update Workspace
  - Update Workspace Member

## Backstage
We provide a Backstage software catalog entity for the Anthropic API & MCP Sandbox, allowing this sandbox to be registered with any catalog, making it discoverable by team and across an organization--allowing anyone to fork and deploy locally within the enterprise.

  - [Anthropic Admin API](backstage/anthropic-admin-api-api-sandbox-backstage.yml)
  - [Anthropic Files API](backstage/anthropic-files-api-api-sandbox-backstage.yml)
  - [Anthropic Message Batches API](backstage/anthropic-message-batches-api-api-sandbox-backstage.yml)
  - [Anthropic Prompt Tools API](backstage/anthropic-messages-api-api-sandbox-backstage.yml)
  - [Anthropic Models API](backstage/anthropic-models-api-api-sandbox-backstage.yml)
  - [Anthropic Prompt Tools API](backstage/anthropic-prompts-api-api-sandbox-backstage.yml)
## Support
Please provide any questions or feedback via GitHub issues, or just email kinlane@naftiko.io with feedback. The goal is to keep iterating upon this sandbox using existing OpenAPI, Microcks, and Bruno features, offering value out of the box via this forkable third-party Anthropic API & MCP Sandbox.


# Anthropic Sandbox
This is sandbox for the Anthropic Sandbox API, using an OpenAPI specification with examples, Microcks and Bruno as the sandbox interface, and this GitHub repository as the vehicle for delivering as a localized sandbox, or also enabling the working directly with production APIs.

## APIs.json Index
There is an APIs.yml file in the root of this repository, providing an index of all the artifacts used as part of this capability, providing a machine-readable way to read, manage, and execute the resources available here.

## OpenAPI
This capability uses OpenAPI as the definition, providing a complete definition of all available paths for the Anthropic Sandbox. The OpenAPI for this capability uses examples and Microcks extensions to mock the requests and responses for each API operation, something we will iterate and expand upon with richer examples as the capability evolves.

## Microcks
This capability uses Microcks to deliver the mock API. [You just install Microcks, with the Docker extension being the easiest](https://microcks.io/documentation/guides/installation/docker-desktop-extension/), [import the OpenAPI as a service](openapi/notion-openapi.yml), and you have a mocked API for all APIs, available via REST and MCP APIs--providing a multi-protocol sandbox.

## Bruno
This capability [uses Bruno as the client](https://www.usebruno.com/), leveraging Bruno Collections pre-generated from the OpenAPI and Bruno environments that uses the localhost and port of Microcks to work with the mocked API. You just have to install Microcks, then open the collection provided in this repository, select the available environments, and begin calling the Anthropic Sandbox via the sandbox or production.


## OpenAPIs
These are the OpenAPIs available for the Anthropic Sandbox, which are made available via this sandbox API, which can be imported into Microcks and deployed as a sandbox using their mock feature.

  - [Anthropic Admin Api Openapi](openapi/anthropic-admin-api-openapi.yml)
  - [Anthropic Files Api Openapi](openapi/anthropic-files-api-openapi.yml)
  - [Anthropic Message Batches Api Openapi](openapi/anthropic-message-batches-api-openapi.yml)
  - [Anthropic Messages Api Openapi](openapi/anthropic-messages-api-openapi.yml)
  - [Anthropic Models Api Openapi](openapi/anthropic-models-api-openapi.yml)
  - [Anthropic Prompts Api Openapi](openapi/anthropic-prompts-api-openapi.yml)

## Skills
Each API operation has a dedicated SKILL.md file providing Claude with structured instructions for using that operation, including endpoints, parameters, example requests, and usage guidance. Skills are organized in the `skills/` directory with one subfolder per operation.

### Administrative API Skills
  - [Get Current Organization](skills/get-current-organization/SKILL.md)
  - [List Organization Members](skills/list-organization-members/SKILL.md)
  - [Get Organization Member](skills/get-organization-member/SKILL.md)
  - [Update Organization Member](skills/update-organization-member/SKILL.md)
  - [Remove Organization Member](skills/remove-organization-member/SKILL.md)
  - [List Organization Invites](skills/list-organization-invites/SKILL.md)
  - [Create Organization Invite](skills/create-organization-invite/SKILL.md)
  - [Get Organization Invite](skills/get-organization-invite/SKILL.md)
  - [Delete Organization Invite](skills/delete-organization-invite/SKILL.md)
  - [List Workspaces](skills/list-workspaces/SKILL.md)
  - [Create Workspace](skills/create-workspace/SKILL.md)
  - [Get Workspace](skills/get-workspace/SKILL.md)
  - [Update Workspace](skills/update-workspace/SKILL.md)
  - [Archive Workspace](skills/archive-workspace/SKILL.md)
  - [List Workspace Members](skills/list-workspace-members/SKILL.md)
  - [Add Workspace Member](skills/add-workspace-member/SKILL.md)
  - [Get Workspace Member](skills/get-workspace-member/SKILL.md)
  - [Update Workspace Member](skills/update-workspace-member/SKILL.md)
  - [Remove Workspace Member](skills/remove-workspace-member/SKILL.md)
  - [List API Keys](skills/list-api-keys/SKILL.md)
  - [Get API Key](skills/get-api-key/SKILL.md)
  - [Update API Key](skills/update-api-key/SKILL.md)

### Files API Skills
  - [List Files](skills/list-files/SKILL.md)
  - [Create File](skills/create-file/SKILL.md)
  - [Get File Metadata](skills/get-file-metadata/SKILL.md)
  - [Delete File](skills/delete-file/SKILL.md)
  - [Download File Content](skills/download-file-content/SKILL.md)

### Message Batches API Skills
  - [List Message Batches](skills/list-message-batches/SKILL.md)
  - [Create Message Batch](skills/create-message-batch/SKILL.md)
  - [Retrieve Message Batch](skills/retrieve-message-batch/SKILL.md)
  - [Delete Message Batch](skills/delete-message-batch/SKILL.md)
  - [Retrieve Message Batch Results](skills/retrieve-message-batch-results/SKILL.md)
  - [Cancel Message Batch](skills/cancel-message-batch/SKILL.md)

### Messages & Models API Skills
  - [List Available Models](skills/list-available-models/SKILL.md)
  - [Get A Specific Model](skills/get-a-specific-model/SKILL.md)
  - [Create A Message](skills/create-a-message/SKILL.md)
  - [Count Tokens In A Message](skills/count-tokens-in-a-message/SKILL.md)

### Prompt Tools API Skills
  - [Generate A Prompt](skills/generate-a-prompt/SKILL.md)
  - [Improve A Prompt](skills/improve-a-prompt/SKILL.md)
  - [Templatize A Prompt](skills/templatize-a-prompt/SKILL.md)

## Support
Please provide any questions or feedback via GitHub issues, or just email kinlane@naftiko.io with feedback. The goal is to keep iterating upon this sandboxes using existing OpenAPI, Microcks, and Bruno features, offering value out of the box via this forkable capability.


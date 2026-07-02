# api-contract-commons

Shared contract fragments for Arcadia Editions API repositories.

This repository is intended to hold master YAML files for reusable OpenAPI and
AsyncAPI sections, including environment servers, common headers, security
schemes, protocol bindings, and message traits.

## Files

- `asyncapi-master.yml`: shared AsyncAPI 3.0 components for event-driven APIs.

## Usage

Service-level AsyncAPI documents can reference shared components directly:

```yaml
servers:
  develop:
    $ref: "https://raw.githubusercontent.com/arcadia-editions/api-contract-commons/refs/heads/main/asyncapi-master.yml#/servers/develop"

components:
  messageTraits:
    CommonHeaders:
      $ref: "https://raw.githubusercontent.com/arcadia-editions/api-contract-commons/refs/heads/main/asyncapi-master.yml#/components/messageTraits/CommonHeaders"
```

Keep service-specific channels, operations, payload schemas, and event names in
the service repository. Keep environment-neutral reusable infrastructure details
in this repository.

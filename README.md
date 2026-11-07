# Rubotty API Specification

This repository describes Rubotty's HTTP API in OpenAPI. It contains request and response schemas for messaging, bridge integrations and administration. A generated HTML reference makes the contract easier to browse.

Copyright 2026, Spark Software Development, LLC.

## Features

The [OpenAPI document](openapi.yaml) records paths, parameters, payloads and responses in one place. It is maintained alongside the service and client libraries, so a route change can be reviewed with its contract change.

The messaging routes cover communities, rooms, channels, messages, reactions and live room streams. Bridge routes let a remote system report its own messages and membership changes as part of a shared room.

The administration routes describe the control plane: configuration, access grants, feature settings and the other resources used to operate the service. Bearer keys carry either a single-community developer scope or deployment-wide administrator scope. Ordinary API responses use YAML; health probes and server-sent event streams use their own documented formats.

[API.html](API.html) is generated from the same document with Redoc. Download it and open it in a browser; its renderer and fonts load from a CDN, so it needs a network connection. The contract is still evolving, and clients should check their supported operations against the version they use.

## Configuration

| File or setting | Purpose |
| --- | --- |
| `openapi.yaml` | Source OpenAPI 3.0.3 contract, including server and authentication definitions. |
| `package.json` | Pinned tooling dependencies and the lint/documentation commands. |
| `API.html` | Generated reference output; update it through the build command. |

No service credentials are needed to lint or render the specification. API server URLs and example values belong in the contract as generic examples, not as private deployment settings.

## Build & Deploy

Install Node.js and npm, then run `npm ci`, `npm run lint` and `npm run docs`. Commit the regenerated `API.html` when changing `openapi.yaml`; CI checks that the generated document matches. This repository publishes documentation and a contract, not a running API service.

## License

PolyForm Strict. Source-available, but not open-source. Free for non-commercial use. See [License](LICENSE.MD) for more information.

## Forking and Contributions

PolyForm Strict does not grant general permission to modify or redistribute this software. Our [Contribution Policy](CONTRIBUTING.md) grants limited permissions for contribution forks, review and controlled testing. Rights independently available under applicable law or the hosting platform's terms remain separate.

Contributions are welcome. You retain ownership, but Spark may use and commercially relicense submitted contributions, including under proprietary terms, even if a submission is declined or withdrawn. Read and accept the contribution agreement before submitting a change.

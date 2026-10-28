# ADR-001: Use SAP Integration Suite as the Event Mediation Layer

## Status

Accepted

## Context

Salesforce Platform Events are exposed through the Salesforce Pub/Sub API. The integration scenario requires SAP Integration Suite to consume and process those events without embedding downstream integration logic into Salesforce.

## Decision

Use SAP Integration Suite / SAP Cloud Integration with the Salesforce Pub/Sub Adapter Sender as the integration boundary.

The integration runtime is responsible for:

- Pub/Sub connectivity;
- authentication references;
- event consumption;
- replay configuration;
- event processing;
- routing/transformation;
- operational monitoring.

## Consequences

### Positive

- Decouples Salesforce event publication from downstream consumers.
- Centralizes integration processing.
- Keeps credentials outside business logic.
- Provides SAP Integration Suite monitoring and operational controls.
- Creates a reusable boundary for additional event-driven scenarios.

### Trade-offs

- Introduces an integration runtime dependency.
- Replay and recovery semantics must be designed carefully.
- Downstream idempotency remains necessary.

## Evidence boundary

The project demonstrates the adapter-based event consumption approach. Production-grade recovery, enterprise alerting and downstream contracts are architecture recommendations rather than demonstrated mission features.

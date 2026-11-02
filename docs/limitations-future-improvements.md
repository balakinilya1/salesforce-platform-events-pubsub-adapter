# Limitations and Future Improvements

## 1. Current limitations

### 1.1 No downstream business target

The mission demonstrates event retrieval and processing but does not define a concrete target application.

**Improvement:** define the target system, interface contract and business outcome for a real implementation.

### 1.2 Replay/recovery policy is not business-defined

The adapter exposes replay options, but the mission does not define an enterprise recovery point or data-loss policy.

**Improvement:** define replay ownership, recovery procedures, retention assumptions and business RPO.

### 1.3 Production error architecture is not fully demonstrated

The mission includes adapter error-related settings but does not establish a complete dead-letter/reprocessing architecture.

**Improvement:** add controlled retry, persistent failed-event handling, reprocessing and alerting.

### 1.4 No downstream field mapping

The mission defines the Platform Event schema but not a target-system mapping.

**Improvement:** create an approved target mapping specification.

### 1.5 No SLA / RTO / RPO

No production service levels are provided.

**Improvement:** define measurable operational targets with the business and operations teams.

### 1.6 No CI/CD design

Deployment is demonstrated, but an enterprise CI/CD pipeline is not.

**Improvement:** introduce versioned artifact promotion and automated quality gates.

## 2. Future evolution

Potential extensions, subject to business requirements:

- additional Salesforce Platform Events;
- event routing by event type;
- reusable canonical event processing;
- standardized correlation IDs;
- enterprise alerting;
- automated reprocessing;
- API/event contract governance.

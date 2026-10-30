# Test Strategy

## 1. Test objective

Verify that Salesforce Platform Events are published and consumed correctly through the Pub/Sub Adapter and that expected failure/replay scenarios are controlled.

## 2. Functional tests

| ID | Scenario | Expected result |
|---|---|---|
| T01 | Account created | Platform Event published |
| T02 | Account updated | Platform Event published |
| T03 | Event received on expected channel | Adapter retrieves event |
| T04 | Latest replay approach | New events are consumed |
| T05 | Earliest replay approach | Retained earlier events are consumed |
| T06 | Custom replay position | Consumption starts from specified position |
| T07 | Invalid replay ID | Configured invalid-replay behavior is invoked |
| T08 | Valid authentication | Connection succeeds |
| T09 | Invalid authentication | Connection/processing failure is visible |
| T10 | Duplicate event | Duplicate handling prevents unintended duplicate processing |

## 3. Integration tests

- Salesforce Platform Event publication
- Salesforce Pub/Sub API connectivity
- Pub/Sub Sender Adapter connectivity
- Security-material references
- Event schema reception
- Replay behavior
- Error processing
- SAP Cloud Integration monitoring

## 4. Negative tests

The production design should additionally test:

- Pub/Sub endpoint unavailable;
- expired/invalid credentials;
- malformed event payload;
- downstream failure;
- repeated event delivery;
- recovery after consumer interruption.

The mission does not provide detailed expected outcomes for all of these scenarios, so they remain portfolio test cases.

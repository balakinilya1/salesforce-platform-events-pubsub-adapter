# Business Requirements

## 1. Business context

The scenario addresses integration scenarios in which Salesforce Platform Events need to be consumed by SAP Integration Suite.

The mission positions the Salesforce Pub/Sub Adapter as the connector for Salesforce Pub/Sub API communication and demonstrates real-time consumption of Platform Events.

## 2. Business objective

Enable SAP Integration Suite to retrieve Salesforce Platform Events and make the event data available for subsequent integration processing.

## 3. Functional requirements

| ID | Requirement | Priority |
|---|---|---|
| BR-01 | The solution shall create a Salesforce Platform Event for Account data. | Must |
| BR-02 | The Platform Event shall be published when an Account is created or updated. | Must |
| BR-03 | Salesforce shall publish the event through the Salesforce Pub/Sub API. | Must |
| BR-04 | SAP Cloud Integration shall consume the event using the Salesforce Pub/Sub Adapter Sender. | Must |
| BR-05 | The integration shall subscribe to the Platform Event channel. | Must |
| BR-06 | The consumer shall support a defined replay-position approach. | Must |
| BR-07 | Authentication credentials shall be maintained outside integration-flow logic. | Must |
| BR-08 | Retrieved event data shall be available for downstream integration processing. | Must |
| BR-09 | The integration shall be deployable and observable in SAP Integration Suite. | Must |

## 4. Event scope

The mission creates the following Platform Event:

**API Name:** `AccountPlatformEvent__e`

The demonstrated event contains Account-related fields including:

- Account ID
- Account Source
- Annual Revenue
- Billing City
- Billing Country
- Billing Street
- Created Date
- Currency ISO Code
- Industry
- Is Deleted
- Last Modified Date
- Name
- Rating
- SAP Customer Number

## 5. Non-functional requirements

| ID | Requirement |
|---|---|
| NFR-01 | Credentials must not be hard-coded in the integration flow. |
| NFR-02 | Event consumption must use a supported Salesforce Pub/Sub connection. |
| NFR-03 | Replay behavior must be explicitly configured. |
| NFR-04 | Integration execution must be observable through SAP Integration Suite monitoring. |
| NFR-05 | Production resilience and recovery policies must be defined before productive use. |

The final requirement is a portfolio architecture recommendation, not a mission claim.

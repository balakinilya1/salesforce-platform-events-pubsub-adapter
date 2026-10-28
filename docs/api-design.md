# API / Interface Design

## 1. Design objective

The mission uses the Salesforce Pub/Sub API through the Salesforce Pub/Sub Adapter. The primary interface is an event-stream contract rather than a conventional REST resource.

## 2. Salesforce Platform Event

**Event API Name:** `AccountPlatformEvent__e`

**Channel:**

`/event/AccountPlatformEvent__e`

**Publisher:** Salesforce Apex

**Consumer:** SAP Cloud Integration through the Salesforce Pub/Sub Adapter Sender

## 3. Logical event contract

| Event field | Business meaning |
|---|---|
| AccountId | Salesforce Account identifier |
| AccountSource | Account source |
| AnnualRevenue | Account annual revenue |
| BillingCity | Billing city |
| BillingCountry | Billing country |
| BillingStreet | Billing street |
| CreatedDate | Account creation timestamp |
| CurrencyIsoCode | Account currency |
| Industry | Account industry |
| IsDeleted | Account deletion indicator represented in the event |
| LastModifiedDate | Account last modification timestamp |
| Name | Account name |
| Rating | Account rating |
| SAPCustomerNumber | SAP customer reference |

The mission defines these as Platform Event fields. It does not provide a complete enterprise canonical model or downstream API contract.

## 4. Consumer interface

The Salesforce Pub/Sub Sender Adapter connects to:

- Host: `api.pubsub.salesforce.com`
- Port: `7443`
- Tenant ID: Salesforce Organization ID
- Channel: `/event/AccountPlatformEvent__e`

## 5. Replay contract

The consumer must define its starting position:

| Approach | Meaning |
|---|---|
| Latest | New events only |
| Earliest | Earlier retained events |
| Custom | Start from a specific replay position |

The adapter also supports a replay preset when an invalid replay ID is encountered.

## 6. Contract gaps

The mission does not specify:

- downstream target endpoint;
- target payload;
- enterprise API versioning policy;
- formal schema registry;
- SLA;
- RPO/RTO;
- end-to-end correlation contract.

These are therefore not invented in this case study.

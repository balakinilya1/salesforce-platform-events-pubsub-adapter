# Data Mapping

## 1. Mapping approach

The mission explicitly defines the fields of the Salesforce Platform Event and shows the Apex trigger populating those fields from the Account object.

It does not define a downstream target mapping. Therefore, this document stops at the **Account → Platform Event** boundary.

## 2. Account to Platform Event mapping

| Salesforce Account | Platform Event |
|---|---|
| `Id` | `AccountId__c` |
| `AccountSource` | `AccountSource__c` |
| `AnnualRevenue` | `AnnualRevenue__c` |
| `BillingCity` | `BillingCity__c` |
| `BillingCountry` | `BillingCountry__c` |
| `BillingStreet` | `BillingStreet__c` |
| `CreatedDate` | `CreatedDate__c` |
| `CurrencyIsoCode` | `CurrencyIsoCode__c` |
| `Industry` | `Industry__c` |
| `IsDeleted` | `IsDeleted__c` |
| `LastModifiedDate` | `LastModifiedDate__c` |
| `Name` | `Name__c` |
| `Rating` | `Rating__c` |
| `SAPCustomerNumber__c` | `SAPCustomerNumber__c` |

The exact API field suffixes are based on the Apex code shown in the mission; the mission screenshot OCR makes some characters difficult to read, so field names should be validated against the actual Salesforce org before implementation.

## 3. Transformation

The demonstrated Apex trigger copies Account values into the event.

No additional transformation rules are specified by the mission.

## 4. Downstream mapping

The downstream mapping is intentionally **TBD** because the mission does not define a target application or target payload.

This prevents the portfolio from presenting invented field mappings as implementation facts.

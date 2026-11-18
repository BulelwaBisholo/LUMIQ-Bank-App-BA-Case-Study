# RTM, UAT, RAID and KPIs

> Fictional portfolio simulation. Test scenarios are proposed; no production execution is claimed.

## Requirements Traceability Matrix

| Business requirement | Functional requirement | User story | UAT |
|---|---|---|---|
| BR-01 | FR-01, FR-02, FR-03 | US-01, US-02 | UAT-01, UAT-02 |
| BR-01 | FR-04 | US-03 | UAT-03 |
| BR-02 | FR-05, FR-07 | US-04, US-05 | UAT-04, UAT-05 |
| BR-03 | FR-06, FR-09 | US-06, US-07 | UAT-06 |
| BR-04 | FR-07, FR-08 | US-04, US-06, US-08 | UAT-04, UAT-06, UAT-07 |
| BR-02 | FR-09 and reporting definition | US-09 | UAT-08 |

## UAT scenarios

| ID | Scenario | Expected result |
|---|---|---|
| UAT-01 | Payment still processing | App shows Processing/Pending, details visible, load within agreed 3-second target; fail if Successful appears. |
| UAT-02 | Success confirmed | Successful appears only after authoritative confirmation. |
| UAT-03 | Proof of payment | Available after confirmed success. |
| UAT-04 | Status notification | One appropriate notification; duplicate event notifications suppressed. |
| UAT-05 | Failed payment | Failed status and safe next step; no misleading success. |
| UAT-06 | Unresolved payment | Case routed with reference, owner and audit trail. |
| UAT-07 | Funds correction | Accurate update; correction follows approved original-method rule. |
| UAT-08 | Operations reporting | Enquiries, escalations and resolution times reconcile to source data. |

**UAT-01 critical negative condition:** if a payment is still processing but the app displays Successful, the test fails. Capture actual result and evidence during execution. Business owner signs off only after agreed exit criteria and critical defects are resolved.

## RAID register

| ID / type | Item | Response |
|---|---|---|
| R-01 Risk | Status data may be delayed or inconsistent. | Validate authoritative source; define fallback and reconciliation. |
| R-02 Risk | Retry may create duplicate attempts. | Idempotency, bounded retries and duplicate monitoring. |
| R-03 Risk | Notification delivery may fail. | Log delivery; retain in-app status as source of truth. |
| A-01 Assumption | Transaction reference and status history can be exposed. | Validate during technical discovery. |
| A-02 Assumption | Operations can define achievable exception targets. | Agree by payment type and exception category. |
| I-01 Issue to validate | Current status labels and ownership are unknown in this simulation. | Confirm through interviews and walkthroughs. |
| D-01 Dependency | Payment APIs and notification infrastructure. | Technical discovery and dependency mapping. |

## KPI definitions
- Status-related contact rate = payment-status enquiries / total payments.
- Payment exception rate = payments entering exception state / total payments.
- Escalation rate = cases escalated to Payments Operations / total payment cases.
- Time to resolution = elapsed time from exception creation to confirmed resolution.
- Proactive update coverage = eligible cases receiving required updates / eligible cases.
- Duplicate payment incident rate = confirmed duplicate incidents / total payments.
- Customer satisfaction after resolution = post-resolution survey score.

No baseline or improvement percentage is claimed. Agree targets only after validating data quality and establishing a baseline.

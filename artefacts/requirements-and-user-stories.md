# Requirements and User Stories

> Fictional portfolio simulation. Requirements and scenarios are illustrative and require validation.

## Business requirements
- **BR-01:** Customers can understand the current payment status from transaction history.
- **BR-02:** Reduce avoidable payment-status enquiries and improve customer confidence.
- **BR-03:** Unresolved exceptions have clear operational ownership and a trackable resolution path.
- **BR-04:** Customers receive appropriate updates when status changes or investigation is required.

## Functional requirements
- **FR-01:** Display current status using agreed status vocabulary.
- **FR-02:** Display date/time, amount, permitted destination details and unique reference.
- **FR-03:** Display Successful only after authoritative confirmation.
- **FR-04:** Make proof of payment available after confirmed success.
- **FR-05:** Support controlled status refresh/retry without duplicate transactions.
- **FR-06:** Route unresolved exceptions to Payments Operations with context.
- **FR-07:** Send configured customer notifications for material status changes.
- **FR-08:** Provide a pre-populated support journey.
- **FR-09:** Audit status changes and relevant actions.

## Non-functional requirements
- **NFR-01:** Transaction details load within the proposed 3-second target under agreed conditions; validate with technical stakeholders.
- **NFR-02:** Authenticated access and appropriate MFA controls protect transaction details.
- **NFR-03:** Customers see only information they are authorised to access.
- **NFR-04:** Status view degrades gracefully if downstream status services are unavailable.
- **NFR-05:** Status changes, retries, notifications and interventions are auditable.
- **NFR-06:** Status labels and next steps are understandable to non-technical customers.

## Business rules
- **RULE-01:** Never show Successful before authoritative confirmation.
- **RULE-02:** Proof of payment is available only after confirmed success.
- **RULE-03:** Retries are bounded and protected by stable transaction IDs/idempotency.
- **RULE-04:** Every unresolved exception has an operational owner and tracked lifecycle.
- **RULE-05:** Bank-side errors should be corrected through release/return to the original method where supported, without requiring a customer claim where the bank can resolve it directly.
- **RULE-06:** Notifications follow privacy, consent and security rules.

## Nine user stories
1. **US-01 Status visibility:** As a customer, I want to see the current payment status so that I know what happened.
2. **US-02 Transaction details:** As a customer, I want the payment details and reference so that I can identify it.
3. **US-03 Proof of payment:** As a customer, I want proof of payment after success so that I can share evidence.
4. **US-04 Notifications:** As a customer, I want status-change updates so that I am not left uncertain.
5. **US-05 Failed payment guidance:** As a customer, I want clear guidance when a payment fails so that I know what to do.
6. **US-06 Escalation:** As a customer, I want unresolved payments investigated without repeating information.
7. **US-07 Exception handling:** As a Payments Operations user, I want a complete exception record so I can investigate efficiently.
8. **US-08 Funds correction:** As a customer, I want to know when funds will be released or returned after a bank-side error.
9. **US-09 Operations reporting:** As an Operations Manager, I want exception and enquiry reporting to monitor service performance.

Each story's detailed acceptance criteria are in the main case-study document.

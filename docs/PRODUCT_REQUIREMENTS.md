# Product Requirements Document

## 1. Objective

Build and validate a pilot that detects product-availability gaps, accepts customer reports, prioritizes the combined signals, and closes the loop with the market and brand operator.

## 2. MVP outcomes

- Detect low-stock or out-of-stock states for a controlled product set.
- Let a customer report a missing product without installing an app.
- Merge duplicate and related signals by market, product, and time window.
- Route a prioritized alert to the appropriate market and brand operator.
- Track acknowledgement, action, and resolution.
- Provide a location-based operational dashboard.

## 3. Functional requirements

### FR-1 | Market onboarding

- Create a unique market record with location, contacts, supported products, and operating hours.
- Generate a unique QR code linked to that market.
- Allow an administrator to activate, pause, or retire a market.

### FR-2 | Camera inventory signal

- Receive a timestamped camera frame or detection event.
- Map the detected item to a supported product and market.
- Classify availability as **available**, **low**, **out**, or **uncertain**.
- Store model confidence and send uncertain cases to review.
- Suppress repeated identical alerts within a configurable window.

### FR-3 | Customer report

- Open a mobile web form from the market QR code.
- Display the market name and supported products.
- Let the customer select “missing product” or “request a product.”
- Accept optional notes and contact details.
- Confirm submission and show an anonymous report status token.

### FR-4 | AI triage

- Classify the report by market, product, intent, and urgency.
- Compare the report with recent camera signals and other reports.
- Assign a confidence and priority score.
- Flag likely spam, duplicates, or conflicting reports.

### FR-5 | Alerts and response

- Notify the designated market and brand operator.
- Include market, product, evidence, severity, confidence, and timestamp.
- Allow the recipient to acknowledge, reject, or mark an action in progress.
- Record a resolution reason and completion time.

### FR-6 | Dashboard

- Show active alerts by priority and age.
- Filter by product, market, city, status, and date.
- Display availability state on a map or location list.
- Show trend summaries for recurring gaps, response time, and verified reports.

### FR-7 | Rewards

- Create a reward ledger for validated customer reports.
- Prevent awarding points to duplicate, rejected, or fraudulent reports.
- Show the customer whether a report was verified and rewarded.

### FR-8 | Competitor observation

- During a pilot, record only aggregate competitor availability signals approved by the business and market.
- Keep this feature behind an administrative flag until privacy, legal, and operational review is complete.

## 4. Non-functional requirements

| Area | Requirement |
|---|---|
| Performance | Customer form loads in under 3 seconds on a typical mobile connection; alert generated within 60 seconds of an accepted signal |
| Reliability | Failed events are retried and visible in an operations queue |
| Security | Encrypt data in transit and at rest; role-based dashboard access |
| Privacy | Do not perform facial recognition; minimize customer identity collection; define image retention before pilot |
| Accessibility | Mobile flow supports keyboard navigation, readable contrast, and clear Arabic/English labels |
| Auditability | Every alert and status change records actor, timestamp, and reason |
| Observability | Track device health, event latency, model confidence, and notification delivery |

## 5. Acceptance at pilot level

The pilot is considered successful when the team can demonstrate an end-to-end closed loop, from a real or staged shelf gap to a recorded operator resolution, while meeting the MVP success thresholds in [Metrics](METRICS_AND_ANALYTICS.md).

## 6. Out of scope for MVP

- Automated ordering or payment.
- Full ERP/POS replacement.
- Dynamic pricing.
- Recognition of every product or store layout.
- Facial recognition or customer surveillance.
- Public consumer availability search across all markets.


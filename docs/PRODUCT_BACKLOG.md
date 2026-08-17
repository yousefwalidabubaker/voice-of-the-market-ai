# Product Backlog

## Prioritization model

- **P0:** required to test the core value proposition.
- **P1:** materially improves trust, usability, or operational value.
- **P2:** scale or differentiation after the core loop is proven.
- Estimates use relative story points: 1, 2, 3, 5, 8, 13.

## Backlog

| ID | Epic | Priority | User story | Acceptance criteria | Points | Release |
|---|---|---:|---|---|---:|---|
| MKT-01 | Market setup | P0 | As an admin, I want to create a market profile so signals route to the correct location. | Required location and contact fields validate; market receives a unique ID; record can be paused. | 3 | MVP |
| MKT-02 | Market setup | P0 | As an admin, I want a unique QR code for each market so the reporting form identifies the location automatically. | QR opens the correct market; invalid/retired code shows a safe error; downloadable print asset generated. | 3 | MVP |
| CAM-01 | Vision signal | P0 | As an operator, I want camera events linked to a market and product so I can see availability. | Event includes market, product, state, confidence, and time; malformed events are rejected and logged. | 5 | MVP |
| CAM-02 | Vision signal | P0 | As an operator, I want products classified as available, low, out, or uncertain so I know what action is needed. | Controlled test set meets agreed accuracy; uncertainty threshold is configurable; uncertain events enter review. | 8 | MVP |
| CAM-03 | Vision signal | P1 | As an operator, I want repeated identical camera events suppressed so alerts remain useful. | Events inside the configured window merge; severity increases still create an update; merge history is visible. | 3 | MVP |
| CAM-04 | Device ops | P1 | As an admin, I want device-health alerts so a silent camera failure is not mistaken for product availability. | Offline status detected; last-seen time displayed; assigned operator notified. | 5 | Pilot+ |
| REP-01 | Customer report | P0 | As a customer, I want a mobile report form after scanning the QR so I can report a missing product quickly. | Correct market preselected; report type and product required; form works without app/account; completion target under 30 seconds. | 5 | MVP |
| REP-02 | Customer report | P0 | As a customer, I want confirmation after submission so I know the report was received. | Confirmation includes status token; no sensitive data appears in URL; duplicate taps create one report. | 2 | MVP |
| REP-03 | Customer report | P1 | As a customer, I want to request a product that is not listed so the brand can see unmet demand. | Search and “other” option available; request stored separately from out-of-stock incident. | 3 | Pilot+ |
| TRI-01 | AI triage | P0 | As an operator, I want reports classified by intent and product so I do not manually sort every submission. | Supported categories map correctly in benchmark set; low-confidence cases are flagged for review. | 5 | MVP |
| TRI-02 | AI triage | P0 | As an operator, I want related reports and camera events correlated so I can trust the alert. | Correlation uses market, product, and time window; alert shows contributing evidence; rule is auditable. | 8 | MVP |
| TRI-03 | AI triage | P0 | As an operator, I want incidents prioritized so I act on the most urgent gaps first. | Priority uses severity, recency, confidence, demand, and repetition; score explanation visible. | 5 | MVP |
| TRI-04 | AI triage | P1 | As an operator, I want suspected spam and duplicate reports flagged so they do not create noise or rewards. | Duplicate threshold configurable; flagged report does not trigger reward; reviewer can override. | 5 | Pilot+ |
| ALT-01 | Alerts | P0 | As a market manager, I want a specific availability alert so I can check the shelf and respond. | Alert identifies product, market, severity, evidence, and time; delivery status recorded. | 5 | MVP |
| ALT-02 | Alerts | P0 | As a brand operator, I want the same incident visible so I can coordinate replenishment. | Role-appropriate notification sent; deep link opens incident; access restricted to authorized user. | 3 | MVP |
| ALT-03 | Workflow | P0 | As a recipient, I want to acknowledge, reject, or start action so everyone knows the incident status. | Status change requires actor and time; rejection requires reason; duplicate transitions prevented. | 5 | MVP |
| ALT-04 | Workflow | P0 | As an operator, I want to close an incident with an outcome so response time can be measured. | Resolution reason required; closed time captured; reopen supported with history. | 3 | MVP |
| DSH-01 | Dashboard | P0 | As an operator, I want an active incident queue sorted by priority so I can focus my work. | Default sort is priority then age; filters persist in session; counts match incident data. | 5 | MVP |
| DSH-02 | Dashboard | P0 | As an operator, I want location and product filters so I can investigate a specific problem. | Filter by city, market, product, state, and date; empty state explains next step. | 3 | MVP |
| DSH-03 | Dashboard | P1 | As a sales lead, I want a city-level availability view so I can spot geographic patterns. | Map/list view displays current state; data freshness visible; low-sample warning shown. | 5 | Pilot+ |
| DSH-04 | Analytics | P1 | As a product manager, I want trend metrics so I can evaluate whether the pilot works. | Dashboard reports discovery time, acknowledgement time, resolution time, valid-report rate, and camera accuracy. | 5 | Pilot+ |
| RWD-01 | Rewards | P1 | As a customer, I want points for a verified report so useful participation is recognized. | Points awarded only after verification; ledger is idempotent; customer can see result. | 8 | Pilot+ |
| RWD-02 | Rewards | P1 | As an operator, I want reward controls so fraudulent reports cannot generate value. | Daily limits, duplicate blocking, and manual suspension available; all changes audited. | 5 | Pilot+ |
| CMP-01 | Market insight | P2 | As a strategy lead, I want approved aggregate competitor-availability trends so I can understand shelf context. | Feature is opt-in per market; no personal data; results aggregate above a minimum sample. | 8 | Scale |
| SEC-01 | Security | P0 | As an admin, I want role-based access so users see only relevant markets and actions. | Roles enforced server-side; unauthorized requests rejected; access changes audited. | 5 | MVP |
| PRV-01 | Privacy | P0 | As a participant, I want a clear privacy notice so I understand what the system captures. | Notice covers images, reports, retention, and contact; available in Arabic and English. | 3 | MVP |
| OPS-01 | Reliability | P1 | As an operator, I want failed events retried and visible so data loss does not remain hidden. | Retry policy documented; dead-letter queue visible; manual replay audited. | 5 | Pilot+ |

## Suggested sprint sequence

### Sprint 0 | Validate and instrument

- MKT-01, MKT-02, SEC-01, PRV-01
- Define supported products, test imagery, baseline process, and analytics events.

### Sprint 1 | Create the two signals

- CAM-01, CAM-02, REP-01, REP-02

### Sprint 2 | Turn signals into action

- TRI-01, TRI-02, TRI-03, ALT-01, ALT-02

### Sprint 3 | Close the loop

- ALT-03, ALT-04, DSH-01, DSH-02, CAM-03

### Pilot hardening

- CAM-04, TRI-04, DSH-04, OPS-01, RWD-01, RWD-02


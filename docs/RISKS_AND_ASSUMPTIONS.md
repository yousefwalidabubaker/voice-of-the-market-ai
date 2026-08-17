# Risks, Assumptions, and Open Questions

## Risk register

| Risk | Likelihood | Impact | Mitigation | Owner |
|---|---|---|---|---|
| Product packaging, reflections, or occlusion reduce detection accuracy | High | High | Controlled product set, store-specific calibration, confidence threshold, manual review | ML lead |
| Camera or network failure creates false confidence | Medium | High | Device heartbeat, offline alerts, last-seen indicator, retry queue | Engineering |
| Customers submit duplicate or fraudulent reports for rewards | High | Medium | Delay rewards until verification, rate limits, duplicate detection, anomaly review | Product/Ops |
| Too many alerts cause operators to ignore the system | Medium | High | Incident merging, priority scoring, suppression windows, alert-volume budget | Product |
| Market employees view the workflow as extra work | Medium | High | One-tap acknowledgement, co-design, clear ownership, pilot training | Product/Ops |
| Images capture people or sensitive information | Medium | High | Camera placement focused on products, no facial recognition, minimization, retention policy, privacy notice | Privacy lead |
| Brand and market disagree about incident ownership | Medium | Medium | Shared status model, escalation rules, named owners, service expectations | Business owner |
| Competitor monitoring creates legal or relationship concerns | Medium | High | Disable by default; use only with approval and aggregate outputs | Legal/Business |
| Hardware and maintenance cost exceed operational value | Medium | High | Small pilot, total-cost model, compare camera+QR vs. QR-only approach | Product/Finance |
| Pilot metrics look good but do not translate to sales impact | Medium | Medium | Track operational leading indicators first; use controlled business evaluation later | Analytics |

## Assumptions to validate first

1. Shelf gaps occur often enough to justify a faster detection mechanism.
2. A designated person can act when an alert arrives.
3. The selected products can be recognized reliably in real refrigerators.
4. Customers will scan a visible QR code when the flow is fast.
5. Markets permit the required hardware and data collection.
6. Faster visibility changes replenishment behavior, not only reporting volume.

## Open product questions

- Who owns an incident when the market says stock is unavailable but the distributor shows inventory?
- What minimum confidence should create an alert vs. a review task?
- Which products have enough value and visual distinctness for the first pilot?
- What is the correct reward: points, coupons, recognition, or none?
- Should customers be notified after restock, and through which consented channel?
- What retention period is necessary for images and derived events?
- Which existing business system should receive resolved incidents at scale?
- Can a QR-only version generate enough value before hardware deployment?

## Kill criteria

Pause or stop the pilot if:

- camera precision remains below 80% after calibration;
- fewer than 30% of valid alerts receive an operational response;
- the workflow has no named business owner;
- privacy or store-consent requirements cannot be satisfied;
- the cost per resolved incident is higher than the value of the action with no credible path to improvement.


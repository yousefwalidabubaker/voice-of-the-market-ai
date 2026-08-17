# User Flows

## 1. Customer reports a missing product

1. Customer cannot find a product.
2. Customer scans the market's QR code.
3. Mobile page opens with market already identified.
4. Customer chooses **Missing product** and selects the product.
5. Customer optionally adds a note or contact method.
6. System validates the submission and checks recent duplicates.
7. Customer receives a confirmation and status token.
8. Report joins any matching camera event or existing incident.
9. After verification, eligible reward points are recorded.

### Failure paths

- Invalid QR: explain that the code is inactive and offer support.
- No connection: preserve the form locally and retry when possible.
- Duplicate report: confirm receipt without creating another incident or reward.
- Unsupported product: store it as a product request rather than an out-of-stock event.

## 2. Camera detects a shelf gap

1. Device captures or evaluates a scheduled view.
2. Model identifies supported product positions.
3. Availability state and confidence are calculated.
4. Low-confidence result goes to review.
5. Accepted result is compared with the previous state.
6. A meaningful change creates or updates an incident.
7. Recent customer reports increase or challenge the confidence.

## 3. Market responds to an alert

1. Market manager receives a priority alert.
2. Manager opens the incident and sees the product, evidence, and timestamp.
3. Manager chooses:
   - **Available:** shelf is stocked; event may be incorrect.
   - **Restocking:** stock exists and is being placed.
   - **Needs order:** market requires replenishment.
   - **Not carried:** product is not part of the market assortment.
4. The brand operator sees the same status.
5. Manager resolves the incident after action.

## 4. Brand operator prioritizes response

1. Operator opens the active incident queue.
2. Queue is ranked by severity, recency, confidence, repeated demand, and market importance.
3. Operator filters by city, product, or route.
4. Operator assigns or coordinates replenishment.
5. Resolution time and outcome are captured.
6. Recurring gaps become a trend for commercial review.

## 5. Product manager reviews pilot health

1. Review data quality and device health.
2. Compare discovery and response time with baseline.
3. Inspect false positives, false negatives, duplicates, and rejected reports.
4. Interview customers, market managers, and operators.
5. Decide to iterate, expand, pause, or stop the pilot.


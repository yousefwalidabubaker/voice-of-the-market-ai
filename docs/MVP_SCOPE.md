# MVP Scope

## MVP question

Can combined camera and customer signals identify genuine shelf gaps early enough for a market or brand operator to take measurable action?

## Pilot scope

- **Markets:** 3-5 participating locations.
- **Products:** 5-10 visually distinct Siniora products.
- **Users:** customers, market managers, and a small brand operations team.
- **Duration:** 4-6 weeks after setup and calibration.
- **Languages:** Arabic first, with English support for operators where needed.

## Must have

- Market onboarding and unique QR code.
- Mobile missing-product report.
- Camera availability event ingestion.
- Available/low/out/uncertain classification.
- Duplicate suppression and basic signal correlation.
- Priority-based alerts to market and brand operator.
- Acknowledge/in-progress/resolved workflow.
- Operational dashboard and audit history.
- Basic privacy notice and role-based access.

## Should have

- Customer report status.
- Verified-report reward points.
- City and product trend views.
- Device-health monitoring.
- Manual correction of AI classifications.

## Could have

- Product-request reports.
- Competitor availability trends.
- WhatsApp or SMS alert channel.
- Recommended replenishment quantity.
- Customer restock notification.

## Won't have in MVP

- Fully automated purchase orders.
- Large-scale nationwide deployment.
- Universal computer vision across arbitrary shelves.
- Dynamic promotions or pricing.
- Consumer social features.

## Definition of done

An MVP story is done when:

1. acceptance criteria pass in the pilot environment;
2. events and errors are observable;
3. access and privacy behavior are reviewed;
4. Arabic mobile copy is usable;
5. the happy path and one failure path are tested;
6. the product owner accepts the result against the user outcome.

## Pilot exit criteria

- Camera precision is at or above 90% for the controlled product set.
- At least 75% of valid alerts are acknowledged within 30 minutes during operating hours.
- Median time from verified gap to recorded action improves by at least 30% over baseline.
- At least 60% of customers who open the QR form complete a report.
- Fraud and duplicate controls prevent rewards for at least 95% of known invalid test cases.


# Metrics and Analytics

## North-star metric

**Verified availability gaps resolved within the target service window per active market.**

This combines signal quality with actual operational action. Raw reports or detections alone are not success.

## Core KPI tree

### Detection quality

- Camera precision and recall by product.
- Percentage of events marked uncertain.
- Valid customer-report rate.
- Percentage of incidents supported by both signal types.
- Duplicate and fraud-block rate.

### Speed

- Median time from shelf gap to detection.
- Median time from detection to alert.
- Median time from alert to acknowledgement.
- Median time from acknowledgement to resolution.
- Percentage resolved inside the target service window.

### Adoption

- QR scans per active market.
- Report-form completion rate.
- Weekly active market managers.
- Alert acknowledgement rate.
- Dashboard weekly active users.

### Business and operational outcomes

- Repeat gap rate by market and product.
- Replenishment actions linked to verified incidents.
- Estimated avoided out-of-stock hours.
- Product requests by location.
- Reward cost per verified, actionable report.

## MVP target hypotheses

| Metric | Initial target |
|---|---:|
| Camera precision for controlled products | >= 90% |
| Valid customer-report rate | >= 70% |
| QR form completion | >= 60% |
| Alert delivery latency | <= 60 seconds |
| Alert acknowledgement within 30 minutes | >= 75% |
| Improvement in median time-to-action | >= 30% |
| Known invalid reward cases blocked | >= 95% |

Targets are hypotheses, not achieved results. Baselines should be measured before pilot launch.

## Event taxonomy

| Event | Key properties |
|---|---|
| `market_created` | market_id, city, active_products |
| `qr_scanned` | market_id, timestamp, anonymous_session_id |
| `report_started` | market_id, report_type |
| `report_submitted` | market_id, product_id, report_type, completion_seconds |
| `camera_event_received` | market_id, product_id, state, confidence, device_id |
| `signal_correlated` | incident_id, signal_types, correlation_window |
| `incident_created` | incident_id, product_id, priority, confidence |
| `alert_delivered` | incident_id, recipient_role, channel, latency_ms |
| `incident_acknowledged` | incident_id, actor_role, age_seconds |
| `incident_resolved` | incident_id, resolution_reason, total_seconds |
| `report_verified` | report_id, verification_source, reward_eligible |
| `reward_awarded` | report_id, points, ledger_id |

## Experiment plan

### Experiment 1 | QR conversion

**Hypothesis:** market-specific copy and a three-field flow will achieve at least 60% completion.  
**Test:** compare short and explanatory QR landing pages across matched markets.  
**Decision:** keep the variant with better completion and no material decline in report validity.

### Experiment 2 | Two-signal trust

**Hypothesis:** incidents supported by camera and customer data are acknowledged faster.  
**Test:** compare acknowledgement time for dual-signal vs. single-signal incidents while controlling for severity.  
**Decision:** adjust prioritization weight based on observed behavior.

### Experiment 3 | Alert design

**Hypothesis:** alerts containing a clear recommended next action reduce acknowledgement time.  
**Test:** compare evidence-only alerts with evidence-plus-action alerts.  
**Decision:** standardize the winning template.


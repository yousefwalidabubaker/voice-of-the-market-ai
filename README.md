# Voice of the Market | AI Retail Availability System

> Turning an empty shelf from a lost sale into a real-time system signal.

**Award:** Winner, *Voice of the Market* challenge | AINAK Challenges 2026  
**Team:** The Executive Congress  
**Challenge partner:** Siniora Food Industries  
**Organizer:** Arab Innovation Network (AIN)  
**Host:** Birzeit University  
**Format:** 24-hour national hackathon with university teams from across Palestine

## The engineering problem

A store can technically have inventory recorded in its system while the actual shelf or refrigerator is empty. That gap between recorded stock and real-world availability creates delayed replenishment and lost sales.

Voice of the Market was designed as an AI-assisted system that combines two independent signals:

1. **Visual inventory monitoring** from a camera mounted inside the refrigerator.
2. **Customer reports** submitted through a market-specific QR code.

The system then validates, classifies, prioritizes, and routes those signals so the market and supplier can react faster.

## Proposed system architecture

```text
Refrigerator Camera
        |
        v
Computer Vision Detection ----+
                              |
Customer QR Report ---------->| Ingestion / Validation Layer
                              |
                              v
                     Deduplication + Priority
                              |
                              v
                     Availability Event Store
                         /             \
                        v               v
                 Operations API     Alert Service
                        |
                        v
                     Dashboard
```

### Main components

- **Edge camera input** for product-presence and stock-state detection
- **Computer vision layer** to classify products as available, low, or missing
- **QR reporting flow** for customers to submit an independent availability signal
- **Validation layer** to normalize reports and reject incomplete input
- **Deduplication logic** to avoid treating repeated reports as separate incidents
- **Priority engine** to rank incidents by urgency and business rules
- **Event store** for availability history, timestamps, market, city, and product data
- **Operations API** to expose current and historical availability to the dashboard
- **Alert service** to notify both Siniora and the market when action is needed
- **Dashboard** for product availability, report status, and replenishment follow-up

## System flow

1. The camera observes the refrigerator and detects a low-stock or out-of-stock state.
2. A customer can independently scan the market QR code and report the same issue.
3. Incoming signals are normalized and validated.
4. Duplicate signals are combined instead of creating repeated incidents.
5. The system assigns a priority based on product, market, signal confidence, and timing.
6. An availability event is stored and sent to the relevant teams.
7. The market confirms the current state or starts a replenishment action.
8. Resolution time and updated availability are recorded for later analysis.

## Engineering considerations

### Computer vision reliability

A production version would need to handle changing lighting, partially hidden products, similar packaging, camera angle changes, and confidence thresholds. Model accuracy would have to be evaluated using real refrigerator images rather than assumed from a controlled demo.

### Duplicate and conflicting signals

The camera and customer reports can describe the same problem or disagree with one another. The system therefore needs timestamps, confidence values, product and market identifiers, and idempotent event handling so repeated input does not create noisy alerts.

### Connectivity

A refrigerator-side device cannot assume perfect connectivity. A stronger implementation would queue detections locally and retry delivery when the connection returns.

### Security and privacy

The camera is intended to monitor products, not customers. A production design should limit the field of view, avoid unnecessary personal data, authenticate market devices, validate QR submissions, and protect operational data exposed by the dashboard APIs.

### Observability

Useful production metrics would include detection confidence, false-positive rate, event-processing latency, duplicate rate, unresolved incident age, and alert-delivery failures.

## Repository contents

This repository preserves the design work created around the hackathon solution. The documents in `docs/` cover requirements, user flows, MVP boundaries, metrics, risks, assumptions, and rollout thinking that would act as inputs to an implementation.

The repository currently focuses on **system design and technical planning rather than production source code**. That distinction is intentional so the project is not presented as a completed production AI system.

## My contribution

I worked across the problem definition, system flow, AI-driven solution concept, feature priorities, technical discussions, and final pitch with the team.

For this repository, I focused on turning the hackathon concept into a system that can be reasoned about technically: defining the signals, components, data flow, failure cases, architecture boundaries, and implementation considerations.

## Hackathon result

The Executive Congress won the **Voice of the Market** challenge at AINAK Challenges 2026. It was my third consecutive hackathon award.

## Possible implementation path

A future build could be split into four stages:

1. Build a QR reporting API and basic availability dashboard.
2. Add an event model, deduplication rules, and alert pipeline.
3. Connect a camera prototype and store confidence-scored detections.
4. Evaluate the computer vision model on real refrigerator images and iterate based on measured accuracy.

## Disclaimer

This is a hackathon system-design project and not an official or production Siniora system. Any scale, performance, or business-impact assumptions would need to be validated through a real pilot.

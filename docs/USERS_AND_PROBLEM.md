# Users and Problem

## Primary problem statement

Brands and markets do not always know when a product is unavailable at the point of purchase. Inventory records, delivery schedules, and occasional store visits can miss the real shelf condition, while customer complaints arrive late or through channels that are difficult to act on.

## Primary personas

### 1. Customer

**Goal:** Find the product they came to buy.  
**Pain:** The product is missing, and there is no fast way to report it or know whether it will return.  
**Job to be done:** “When I cannot find a product, help me report it in seconds and know that the right people received the report.”

### 2. Market manager

**Goal:** Keep high-demand products available without adding operational overhead.  
**Pain:** Receives late, fragmented, or duplicate complaints and may not know which gaps are most urgent.  
**Job to be done:** “When availability changes, show me what requires attention and let me acknowledge the action quickly.”

### 3. Brand availability operator

**Goal:** Maintain product presence across many markets.  
**Pain:** Cannot continuously observe every refrigerator or distinguish isolated reports from a meaningful pattern.  
**Job to be done:** “When availability falls, give me trusted, prioritized evidence so I can coordinate the right response.”

### 4. Sales and distribution lead

**Goal:** Allocate replenishment capacity where it protects the most demand.  
**Pain:** Store visits and historical orders do not always reveal current urgency.  
**Job to be done:** “When several markets need stock, rank them using recency, severity, demand, and confidence.”

## Pain-point hierarchy

| Priority | Pain point | Evidence to collect in pilot |
|---|---|---|
| P0 | Out-of-stock events are discovered late | Baseline discovery time vs. system detection time |
| P0 | Alerts lack clear ownership and status | Percentage acknowledged and resolved |
| P1 | Customer reports are noisy or duplicated | Valid-report rate and duplicate rate |
| P1 | Camera detections can be uncertain | Precision, recall, and manual-review rate |
| P2 | Demand for unavailable products is not captured | Product requests per location and conversion after restock |

## Opportunity statement

Create a shared, near-real-time view of retail availability that connects the person who notices the gap with the teams capable of fixing it.

## Assumption map

### Desirability

- Customers will scan a QR code when the flow takes less than 30 seconds.
- Market managers will respond if alerts are specific and easy to acknowledge.
- Brand teams value shelf evidence in addition to ERP or distributor data.

### Feasibility

- Cameras can recognize the selected products in realistic lighting and refrigerator layouts.
- Markets can provide power, connectivity, and permission for a limited pilot.
- A rules-plus-model approach can triage reports with acceptable accuracy.

### Viability

- Faster visibility produces enough operational value to justify the hardware and service cost.
- The workflow fits existing sales and distribution responsibilities.


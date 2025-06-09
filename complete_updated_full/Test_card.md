# Test Cards

## Test Card 1: Environmental Impact Badge Awareness

### Hypothesis
Displaying per-item environmental footprint badges (water & carbon metrics) on product pages will reduce purchase intent among eco-conscious shoppers.
> “Seeing the water badge made me hesitate – I didn’t realize how much water goes into making this shirt.” – Participant 1

### Experiment Design
Randomly assign 200 users to Version A (badges displayed) or Version B (no badges); survey purchase intent before and after browsing.

### Metric
**Purchase-Intent Delta** = Intent_after − Intent_before (percentage points)

### Success Criteria
- Statistically significant negative change (p < 0.05)
- Effect size ≥ 5%

### Risks & Mitigations
- **Risk:** Badge units unfamiliar to users.  
  **Mitigation:** Add tooltip “Water saved vs. new production” on hover.

---

## Test Card 2: Sales Catalog Conversion

### Hypothesis
Streamlining the checkout flow to two steps will increase conversion rates for users adding items to their cart.
> “I thought the payment form was too long – I abandoned my cart halfway.” – Participant 2

### Experiment Design
Track the first 1,000 “Add to Cart” events; instrument “Begin Checkout” and “Order Completed” events; conduct usability interviews with 10 participants.

### Metric
- **Conversion Rate** = Completed_orders ÷ Add-to-cart_actions  
- **Drop-off Rate** between “Begin Checkout” and payment step

### Success Criteria
- Conversion Rate ≥ 12%
- Drop-off Rate ≤ 20%

### Risks & Mitigations
- **Risk:** Users get frustrated by unclear progress indicators.  
  **Mitigation:** Introduce a dynamic progress bar (“Shipping ▶ Payment ▶ Review”).

---

## Test Card 3: Recycling Drop-off Map Interaction

### Hypothesis
At least 30% of map searches will lead to a detail-view click when using custom markers and clustering.
> “I thought there were fewer bins because the markers clustered together.” – Participant 3

### Experiment Design
Track 500 map searches and subsequent “View Details” clicks; interview 15 users on map usability.

### Metric
**Detail-View Rate** = Detail-view_clicks ÷ Map_searches

### Success Criteria
- Detail-View Rate ≥ 30%
- Users report clarity in map legend during interviews

### Risks & Mitigations
- **Risk:** Clusters confuse users about available locations.  
  **Mitigation:** Limit clustering threshold and add “Zoom in to see all” hint.

---

## Test Card 4: Pickup Scheduler Adoption

### Hypothesis
20% of users visiting the Pickup page will schedule an at-home pickup slot within 10 days.
> “I wasn’t sure which slots were morning vs. afternoon.” – Participant 4

### Experiment Design
Track 500 Pickup page views and “Confirm Pickup” submissions; survey 20 users on scheduling barriers.

### Metric
**Scheduling Rate** = Pickups_scheduled ÷ Pickup_page_views

### Success Criteria
- Scheduling Rate ≥ 20%
- Median time-to-schedule ≤ 5 days

### Risks & Mitigations
- **Risk:** Form complexity leads to drop-off.  
  **Mitigation:** Simplify fields and add a progress bar.

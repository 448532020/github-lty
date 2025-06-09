# MVP Test Cards for Hypotheses

## Test Card 1: Home Dashboard Engagement

### Hypothesis
New users will click one of the quick-action buttons on the Home Dashboard if the labels are clear.
> “I tried tapping the button but wasn't sure what would happen next.” – Participant 5

### Experiment Design
Deploy the quick-action UI to 200 new sign-ups; instrument analytics to capture each button click and record device type.

### Primary Metric
**Engagement Rate** = Users_with_≥1_click ÷ Total_users

### Success Criteria
- Engagement Rate ≥ 60% within 5 days
- No significant difference across device types (p > 0.05)

### Risks & Mitigations
- **Risk:** Label confusion reduces clicks.  
  **Mitigation:** Conduct a quick A/B test of labels (“Shop Deals” vs. “Browse Sales”).

### Key Learnings to Capture
- Engagement differences by device
- Feedback on label clarity

---

## Test Card 2: Sales & Checkout Conversion

### Hypothesis
At least 12% of users who add items to their cart will complete checkout within the same session under the new flow.
> “I dropped off during payment because I didn’t see a progress bar.” – Participant 6

### Experiment Design
Track the first 1,000 add-to-cart actions; instrument “Begin Checkout” and “Order Completed” events; interview 10 users on checkout clarity.

### Primary Metric
**Conversion Rate** = Completed_orders ÷ Add-to-cart_actions

### Success Criteria
- Conversion Rate ≥ 12%
- Drop-off between “Begin Checkout” and payment ≤ 20%

### Risks & Mitigations
- **Risk:** Users abandon due to long payment forms.  
  **Mitigation:** Auto-detect card type and reduce fields.

### Key Learnings to Capture
- Impact of first-order discount
- Usability issues in payment fields

---

## Test Card 3: Pickup & Drop-off Flow Adoption

### Hypothesis
At least 25% of users visiting Pickup or Drop-off pages will schedule or view details within 10 days.
> “I clicked but didn’t get any confirmation on next steps.” – Participant 7

### Experiment Design
Instrument “Pickup Page View,” “Confirm Pickup,” “Drop-off Search,” and “View Details” events; survey 20 users.

### Primary Metric
- **Pickup Adoption Rate** = Pickups_scheduled ÷ Pickup_page_views  
- **Detail-View Rate** = Detail-view_clicks ÷ Drop-off_searches

### Success Criteria
- Pickup Adoption ≥ 20%
- Detail-View Rate ≥ 25%

### Risks & Mitigations
- **Risk:** Icon confusion on map.  
  **Mitigation:** Update legend with text labels.

### Key Learnings to Capture
- User sentiment on flow clarity
- Device-based differences

---

## Test Card 4: Profile Completion & Rewards Redemption

### Hypothesis
75% of new users will complete their profile within 48 hours; 18% will redeem at least one coupon within 30 days.
> “I didn’t see the coupon code when I checked out.” – Participant 8

### Experiment Design
Track “Profile Completed” events for 200 sign-ups; track “Coupon Issued” and “Coupon Redeemed” for 500 users; poll 15 users.

### Primary Metric
- **Profile Completion Rate** = Profiles_completed_48h ÷ New_sign-ups  
- **Redemption Rate** = Coupons_redeemed ÷ Coupons_issued

### Success Criteria
- Profile Completion ≥ 75% within 48h
- Redemption Rate ≥ 18% within 30 days

### Risks & Mitigations
- **Risk:** Email delays in coupon delivery.  
  **Mitigation:** Implement SMS fallback for verification and coupon alerts.

# Test Cards (Consolidated)

We’ve grouped our six original hypotheses into four broader Test Cards, each with richer detail to guide execution.

## 1. Dashboard & Quick-Action Engagement  
**Context**  
New users land on the Home Dashboard and see impact metrics plus quick-action buttons.  

**Hypothesis**  
At least **60%** of users who sign up will click one dashboard quick-action (Schedule Pickup, Find Drop-off, Browse Sales) within their first **5 days**.  

**Test Plan**  
- Roll out Dashboard to a beta cohort of **200 new users**.  
- Instrument click events on each quick-action button.  
- Track time from account creation to first click.  

**Metrics**  
- Engagement rate = (# users with ≥1 quick-action click) / (total beta users).  
- Median time to first click.  

**Success Criteria**  
- Engagement rate ≥ 60%.  
- Median time ≤ 48 hours.

**Timeline**  
- Launch analytics tracking Day 0.  
- Evaluate at Day 7.

---

## 2. Purchase & Checkout Conversion  
**Context**  
Users browse the catalog, add items to cart, and proceed through checkout.  

**Hypothesis**  
A **12%** conversion rate from “Add to Cart” to “Order Completed” will be achieved in the first **1000** add-to-cart events.  

**Test Plan**  
- Release Sales & Cart flows publicly.  
- Capture “Add to Cart”, “Begin Checkout”, and “Order Completed” events.  
- Conduct usability interviews (n=10) to surface friction points.  

**Metrics**  
- Conversion rate = completed orders / add-to-cart actions.  
- Drop-off rate at each funnel step.  

**Success Criteria**  
- Conversion ≥ 12%.  
- Drop-off ≤ 20% between “Begin Checkout” and payment.

**Timeline**  
- Data collection over first 2 weeks post-launch.

---

## 3. Pickup & Drop-off Flow Adoption  
**Context**  
Users can either schedule at-home pickups or find drop-off locations via the map.  

**Hypothesis**  
At least **25%** of users who visit either the Pickup or Drop-off page will complete a booking or view location details, respectively, within **10 days**.  

**Test Plan**  
- Instrument page views on Pickup and Drop-off.  
- Track “Schedule Pickup” submissions and “View Location Details” clicks.  
- Survey a subset (n=20) about clarity of the flow.  

**Metrics**  
- Pickup adoption rate = pickups scheduled / pickup page views.  
- Drop-off detail-view rate = detail clicks / drop-off searches.  

**Success Criteria**  
- Pickup adoption ≥ 20%.  
- Detail-view rate ≥ 25%.

**Timeline**  
- Monitor for 10 days after feature enablement.

---

## 4. Account Completion & Rewards Redemption  
**Context**  
Users must fill out profile details and engage with the rewards system.  

**Hypothesis**  
- **Profile Completion**: ≥ 75% of new users will finish their profile (including avatar & address) within **48 h**.  
- **Rewards Redemption**: ≥ 18% of users with issued coupons will redeem at least one within **30 days**.  

**Test Plan**  
- Track “Profile Completed” events triggered when all fields are filled.  
- Issue one demo coupon to each new user; track “Redeem” clicks.  
- Conduct quick polls (n=15) on barriers to completion/redemption.  

**Metrics**  
- Profile completion rate / time-to-completion.  
- Redemption rate = redeemed coupons / issued coupons.  

**Success Criteria**  
- Profile completion ≥ 75% within 48 h.  
- Redemption rate ≥ 18% within 30 days.

**Timeline**  
- Profile: measure over rolling cohort of 200 new sign-ups.  
- Rewards: measure 30 days post-coupon issue.

# Value Proposition Canvas

## 1. Customer Profile

### Customer Jobs
- **Discover & Act on Impact**
  - Check personalized sustainability dashboards to see how individual actions (purchases, recycling) translate to water and carbon savings.
  - Decide between drop-off or pickup for recycling based on convenience.
- **Acquire Sustainable Apparel**
  - Browse and purchase second-hand clothing at affordable prices.
  - Filter by style, size, condition, and environmental impact to match taste and values.
- **Dispose of Unwanted Clothing**
  - Locate the nearest drop-off point or schedule a home pickup for recycling.
  - Quickly take photos or type a list of items and confirm a pickup slot with minimal friction.
- **Manage Account & Rewards**
  - View order history, recycling history, and points balance from a single “Profile & Account Hub.”
  - Redeem points for coupons or donate points to charity partners.

### Pains
- **Complex Recycling Options**
  - Hard to find drop-off bins or understand which locations accept textiles vs. only certain fabrics.
  - Difficulty coordinating a home pickup time slot due to limited availability or confusing UI.
- **Uncertainty of Impact**
  - Lack of clear feedback on how much water or CO₂e is actually saved by purchasing a second-hand item.
  - No single place to see aggregate impact—users end up feeling their efforts are fragmented.
- **Checkout Friction**
  - Long multi-step forms deter users from completing a purchase.
  - Lack of guest-checkout forces new users to register first, leading to cart abandonment.
- **Profile Setup Friction**
  - Multiple screens to enter personal details and address, causing drop-off rates during registration.
  - Difficulty uploading a profile picture due to unclear file size/type restrictions.
- **Low Reward Visibility**
  - Coupons or points expire unnoticed; users forget to check email or in-app notifications.
  - Redemption process is cumbersome: manual entry of code at checkout without clear feedback.

### Gains
- **Clarity & Motivation**
  - Instant feedback on water saved, carbon reduced, and total items recycled—encourages continued engagement.
  - Composite Sustainability Score gives a single metric to share on social media (e.g., “I saved 120L of water this month!”).
- **Convenience**
  - One-stop interface for shopping, recycling, and scheduling pickups so users don’t need multiple apps.
  - Quick-action buttons on the dashboard make it easy to schedule pickup or find a drop-off location in one click.
- **Flexibility**
  - Option to choose between dropping items off at a nearby bin vs. booking a convenient home pickup slot.
  - Filterable sales catalog that surfaces items matching user preferences (size, style, condition).
- **Speed & Simplicity**
  - Streamlined checkout with guest-checkout, address autocomplete, and clear progress indicators.
  - Flatpickr-powered calendar to quickly pick a date and time for pickup; disabled dates make it obvious when slots aren’t available.
- **Recognition & Savings**
  - Visible points meter and milestone badges (e.g., “Recycling Hero”) to gamify the experience.
  - Redeemable coupons that are automatically suggested at checkout; clear expiration dates and in-app reminders.

## 2. Value Map

### Products & Services
1. **Home Dashboard**
   - **Real-time Water & Carbon Metrics:** Graphical display (line charts, bar charts) of cumulative metrics with weekly/monthly toggles.
   - **Quick-Action Buttons:**
     - “Schedule a Pickup”
     - “Find a Drop-off Location”
     - “Browse Sales Catalog”
   - **Composite Sustainability Score Gauge:** Shows overall performance.

2. **Sales Catalog & Cart**
   - **Filterable Product Grid:**
     - Filters: gender, size, color, style, price range, condition.
     - Sort options: Price Low→High, Newest, Trending.
   - **Product Detail Pages:**
     - High-resolution photos, environmental impact badge, detailed condition description, related-items carousel.
     - “Add to Cart” and “Add to Wishlist” buttons.
   - **Guest-Checkout or Registered Checkout:** Two-step process: shipping → payment → review.
   - **Cart Summary & Order Confirmation:** Editable quantities, remove items, shipping cost estimates, tax calculation, and final “Place Order” CTA.

3. **Recycling Drop-off Map**
   - **Interactive Map with Custom Markers:**
     - Geo-located pins for charity bins, recycling centers, and repair shops. Clustering for dense areas.
     - “Mark as Visited” toggle to gray out used locations and log them in user history.
   - **Details Panel for Each Location:**
     - Name, address, hours, accepted items, distance, contact info, “Get Directions” link.
   - **List View Option:** Sort by distance or alphabetical, including “Call for More Info” link if available.

4. **Pickup Scheduler**
   - **Flatpickr Calendar Widget:**
     - Disabled dates for fully booked days; tooltips for special notes (e.g., “Holiday—No Pickups”).
     - Time slots listed under selected date, grouped by morning/afternoon.
   - **Pickup Request Form:**
     - Pickup address (editable), item list uploader (text or up to 5 photos), optional instructions.
     - “Confirm Pickup” button that triggers confirmation email and in-app notification.

5. **Profile & Account Hub**
   - **Edit Personal Info & Avatar**
   - **Recycle History Log with Point Earnings**
   - **Points Meter & Available Coupons**
   - **Order History & Tracking Links**
   - **Help & Support Section**

### Pain Relievers
- **Map + Scheduler Integration**
  - One interface to locate drop-off bins or book home pickups without hopping between apps or websites.
  - “Mark as Visited” feature prevents returning to the same location multiple times and automatically logs the action.
- **Instant Impact Feedback**
  - Composite Sustainability Score aggregates all metrics; users can understand exactly how each action contributes to their progress.
  - Real-time updates encourage immediate gratification and reinforce positive behavior.
- **Streamlined Flows**
  - Guest-checkout reduces the barrier for first-time purchasers; address autocomplete and saved addresses minimize form friction.
  - Two-step checkout with progress indicators keeps users informed of where they are in the process.
- **Unified Profile Center**
  - Single dashboard for orders, recycling history, points, coupons, and profile settings—no need to navigate multiple menu items.
  - “Download History” CSV helps users track their own progress offline.
- **Automated Reminders & Alerts**
  - Email/SMS/app notifications for upcoming pickups, expiring coupons, and new flash sales ensure users don’t miss opportunities.
  - Points reminders at milestones (e.g., “You’re 20 points away from your next coupon!”).

### Gain Creators
- **Quick-Action Prompts**
  - CTA buttons placed prominently on the Home Dashboard drive immediate engagement (e.g., “Schedule Pickup →”).
  - Contextual prompts appear as badges on icons (e.g., “You have 2 unredeemed coupons”).
- **Dynamic Filters & Search**
  - Real-time filtering and search suggestions help users find items quickly (autocomplete shows matching brands and styles).
  - Map search auto-centers on the user’s location or entered address for quick drop-off lookup.
- **Visual Rewards Display**
  - Points meter animation when users earn points (e.g., +10): green “+10” floats up from the meter.
  - Earned badges appear under “Achievement” section of profile, with a brief celebratory animation.
- **Interactive Charts & Trends**
  - Hovering over a data point on the line chart shows “Date: X, Water Saved: Y L, Carbon Saved: Z kg.”
  - Users can toggle metrics to overlay water and carbon trends on the same chart for comparison.
- **Onboarding Tooltips & Micro-surveys**
  - First-time users see guided tooltips: “Click here to browse sales,” “Schedule your first pickup.”
  - Micro-survey after completing first recycling: “How was the drop-off process? (1–5 stars).”

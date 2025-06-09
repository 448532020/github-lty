# Minimum Viable Product Overview

## 1. Home Dashboard
- **Impact Overview**  
  - **Water Saved:** Cumulative liters saved via second-hand purchases and recycling, with weekly/monthly trend charts.  
  - **Carbon Reduced:** Real-time CO₂e savings since signup.  
  - **Items Recycled:** Badges unlocked at 10, 25, 50 items.

- **Composite Sustainability Score**  
  Color-coded gauge (0–100): Red (0–30), Orange (31–60), Green (61–100).

- **Quick Actions**  
  - Schedule a Pickup  
  - Find a Drop-off Location  
  - Browse Sales  
**Risk & Mitigation**  
- **Risk:** Overwhelming first-time users.  
  **Mitigation:** Onboarding tooltip tour.

## 2. Sales Catalog & Cart
- **Filters & Search:** Gender, size, price, condition; autocomplete suggestions.  
- **Product Cards:** Thumbnail, title, price, footprint badge.  
- **Checkout Flow:**  
  1. Shipping Info (autocomplete)  
  2. Payment Info (auto-detect card type)  
  3. Order Review & Confirmation  
**Risk & Mitigation**  
- **Risk:** Payment form abandonment.  
  **Mitigation:** Two-step flow with progress bar.

## 3. Recycling Drop-off Map
- **Interactive Map:** Custom pins (charity bins, recycling centers, repair shops); clustering with “Zoom in” hint.  
- **List View Toggle:** Alternative list sorted by distance.  
- **Details Panel:** Address, hours, accepted items, “Get Directions,” “Mark as Visited.”  
**Risk & Mitigation**  
- **Risk:** Pin/icon confusion.  
  **Mitigation:** Add legend and hover labels.

## 4. Pickup Scheduler
- **Flatpickr Calendar:** Disabled dates greyed out; tooltips for full slots.  
- **Time Slots:** Grouped under Morning/Afternoon with highlights for “Next Available.”  
- **Request Form:** Address, item text/photo input, special instructions.  
- **Reminders:** 24h email/app notifications.  
**Risk & Mitigation**  
- **Risk:** Upload failures on slow networks.  
  **Mitigation:** Text-only fallback option.

## 5. Profile & Account Hub
- **Personal Info & Avatar:** Edit fields; file size/type validations.  
- **My Recycling:** History log, points balance, “Download CSV.”  
- **Orders & Rewards:** Order history, coupons grid, redemption history.  
- **Help & Support:** FAQ accordion, contact form, live-chat placeholder.  
**Risk & Mitigation**  
- **Risk:** Low reward visibility.  
  **Mitigation:** In-app banner “You have unredeemed coupons!”

## Future Enhancements
- Guided onboarding tour  
- Social sharing for eco-achievements  
- Premium subscription tier with exclusive features

# Minimum Viable Product Overview

## Problem Statement
Users lack a single app to shop sustainably, recycle textiles, and schedule pickups—forcing them to juggle multiple platforms.

## Core Features

### Interactive Drop-off Map
- **Search & Filter:** Enter address or ZIP; radius slider (5–20 km).
- **Actions:** Tap any pin for details and “Mark as Visited.”

**Risk & Mitigation**
- **Risk:** Users may misinterpret map icons.
  **Mitigation:** Add legend and hover tooltips.

### At-Home Pickup Scheduler
1. **Pick Date & Time:** Flatpickr calendar with morning/afternoon slots.
2. **Specify Items:** Text list (“3 shirts”) or photo upload.
3. **Confirm & Schedule:** Review and confirm; automatic reminders follow.

**Risk & Mitigation**
- **Risk:** Photo uploads may fail on slow connections.
  **Mitigation:** Provide optional text-entry fallback.

### Rewards & Profile Hub
- **Track Points:** Recycle → 10 pts; purchase → 1 pt/$1.
- **Auto-apply Coupons:** System applies “SAVE10” at checkout.
- **Badges & Milestones:** Celebrate eco-achievements in-app.

**Risk & Mitigation**
- **Risk:** Points system may feel intrusive.
  **Mitigation:** Allow users to hide rewards display.

## Key Metrics
- **Adoption Rate:** Users_who_complete_≥1_action ÷ Total_visits
- **Pickup Scheduling Rate:** Pickups_scheduled ÷ List_page_views

## Future Enhancements
- Introduce guided onboarding tour for first-time users.
- Build social sharing for eco-achievements.

# Business Model Canvas

## 1. Customer Segments
- **Environmentally-conscious Shoppers**
  - Individuals who prioritize reducing their environmental footprint by opting for second-hand purchases and recycling.
  - Value transparency around water and carbon savings for each action they take.
- **Busy Individuals**
  - People with limited free time who seek a streamlined way to recycle textiles (drop-off or home pickup) without having to research local options.
  - Appreciate automated scheduling, reminders, and simple, intuitive interfaces.
- **Budget-conscious Shoppers**
  - Customers looking for quality second-hand apparel at lower prices compared to brand-new items.
  - Motivated by discounts, coupon codes, and reward points that reduce out-of-pocket costs.
- **Value-driven Purchasers**
  - Consumers interested in sustainable products that align with their ethical values; they want visible proof of environmental impact.
  - Likely to engage in repeat buying if there are clear incentives, badges, or recognition.

## 2. Value Propositions
1. **All-in-one Sustainability Hub**
   - Combines personalized impact dashboard, sales catalog of curated second-hand items, interactive recycling map, and pickup scheduling into a single platform.
   - Users can see at a glance how their actions (purchases + recycling) contribute to water and carbon savings.

2. **Wide Selection of Sustainable Items for Purchase**
   - Curated collection of second-hand apparel—each product listing clearly shows estimated water saved and carbon reduced by purchasing that item.
   - Quality checks ensure items meet minimum condition standards (“Like New,” “Good,” “Fair”) with high-resolution photos and honest descriptions.
   - Seasonal sales and flash deals on items that have been in inventory more than 14 days.

3. **Transparent Impact Metrics**
   - Real-time tracking of water saved, carbon emissions reduced, and total items recycled.
   - Composite Sustainability Score to give users a single metric (0–100) summarizing their overall impact.
   - Benchmarking: shows how a user’s metrics compare to local and national averages.

4. **Convenient Recycling & Pickup**
   - **Interactive Map:**
     - Lets users search by address or landmark; radius filter for 5/10/20/50 km; clusters pins when locations are dense.
     - “Mark as Visited” toggle updates user’s recycle history automatically.
   - **Pickup Scheduler:**
     - Flatpickr-based calendar with available slots: date disabled if none available, enforce 2-hour lead time.
     - Two input methods for items: text list or photo upload; special instructions field for driver notes.
     - Automated reminders via email/app 24 hours before, plus follow-up if not confirmed.

5. **Reward-Driven Engagement**
   - Point system where:
     - Recycle an item → 10 points
     - Complete a purchase → 1 point per $1 spent
     - Schedule & complete a pickup → 15 points
     - Refer a friend who makes a first purchase → 50 points
   - Points meter on profile, with badges unlocked at 25, 50, 100 points.
   - Redeem points for coupons (e.g., 100 points = $10 off next purchase) or donate points to partnered charities.
   - In-app progress bars and milestone notifications to encourage continued engagement.

6. **Seamless Shopping Experience**
   - Two-step checkout: gather shipping details first, then payment, followed by order review.
   - Guest-checkout option for first-time or occasional buyers.
   - Autocomplete addresses to reduce form friction; saved addresses for returning users.
   - Related-items carousel on product pages to increase cross-sell opportunities.

## 3. Channels
- **Web & Mobile App**
  - Fully responsive web app; mobile-optimized UI for smaller screens.
  - Push notifications on mobile to remind users of scheduled pickups, expiring coupons, or new flash sales.

- **Social Media & Influencer Partnerships**
  - Collaborate with eco-influencers and sustainable fashion bloggers to showcase unique second-hand finds.
  - Instagram/TikTok campaigns using user-generated content (#MySustainableHaul) and monthly giveaways (e.g., 5 users win $20 coupon for the best styled recycled outfit).

- **Email Campaigns & Push Notifications**
  - Weekly “Your Impact” summary email showing water/carbon saved, items recycled, and points balance.
  - Abandoned cart reminders: “You left items in your cart—complete checkout now for an extra 5% off.”
  - New coupon alerts and flash sale announcements segmented by user behavior (e.g., “20% off shoes for users who browsed shoes in past 7 days”).

- **In-app Banners & Prompts**
  - Contextual banners at the top of dashboards: “Recycle 5 more items to unlock a 10% off coupon.”
  - After completing a purchase: “Get 15 points if you schedule a pickup in the next 48 hours.”

## 4. Customer Relationships
- **Self-service Portal**
  - Intuitive navigation: one-click access to Sales Catalog, Recycling Map, Pickup Scheduler, Rewards Dashboard, and Profile.
  - Tooltips and on-screen guidance (e.g., “Click here to filter by size”).

- **Automated Reminders**
  - Email/SMS/app notifications:
    1. “Your pickup is tomorrow at 2pm—please have items ready.”
    2. “Your coupon SAVE10 expires in 3 days—redeem now!”
    3. “Weekly Impact Report: You saved 50L water, 12kg CO₂e, and recycled 4 items.”

- **In-app Micro-Surveys**
  - Pop-up surveys after key actions:
    - After purchase: “How was your checkout experience? (1–5 stars)”
    - After recycling: “Was the drop-off location easy to find? (Yes/No + optional comment).”

- **Light-touch Support**
  - Searchable FAQ covering Orders & Shipping, Recycling & Pickup, Points & Rewards, Payment & Billing, and Account Settings.
  - Contact form with ability to attach up to two images (e.g., screenshot of error page).
  - Live-chat placeholder with “We’re launching live chat soon” message, plus link to support email.

## 5. Revenue Streams
1. **Sales Commissions**
   - Commission (e.g., 10–20%) on the final sale price of second-hand items sold through the platform.
   - Tiered commission: standard sellers (10%), premium sellers (15–20%) based on volume or quality reviews.

2. **Premium Subscriptions (Future)**
   - Subscription tier ($9.99/month) offering:
     - Early access to new inventory drops.
     - Free expedited shipping on purchases.
     - Priority pickup scheduling (guaranteed next-day slots).
     - Exclusive coupons and double points on recycling events.

3. **Affiliate Fees**
   - Partnerships with local recycling centers and logistics providers—platform receives a referral fee for each scheduled pickup routed through partner networks.

4. **Promotional Partnerships**
   - Sponsored placements for sustainable fashion brands (e.g., “Featured Brand of the Week” section).
   - Co-branded campaigns (e.g., “Recycle 10 items, get 20% off from Brand X”).

## 6. Key Resources
- **Technology Stack**
  - Front-end: React (web), React Native (mobile) or responsive framework (e.g., Next.js).
  - Back-end: Node.js/Express or Django REST API, with PostgreSQL database.
  - Mapping API: Google Maps or Mapbox for interactive recycling map.
  - Notification Engine: Firebase Cloud Messaging (FCM) for push notifications, SendGrid for email.

- **Environmental Data Feeds**
  - Licensed data on water and carbon footprint per garment type (sourced from industry reports, NGOs like WRAP).
  - Real-time updates for benchmarks (average savings per region).

- **Operations Team**
  - Logistics coordinators to manage pickup schedules, driver assignments, and partner relationships.
  - Quality control team to inspect second-hand items, verify condition, and manage inventory listings.
  - Customer support agents to handle inquiries, disputes, and technical issues.

- **Analytics & Experimentation Tools**
  - Event tracking via Google Analytics / Mixpanel to capture user flows (e.g., “Add to Cart → Begin Checkout → Purchase”).
  - A/B testing platform (e.g., Optimizely) for UI/UX experiments like button color, CTA wording, or discount thresholds.
  - Heatmaps (Hotjar) to identify areas where users struggle on key pages (checkout, map, scheduler).

## 7. Key Activities
1. **Platform Development & Maintenance**
   - Ongoing sprints to develop new features: rewards redemption, enhanced filtering, internationalization.
   - Security updates and codebase refactoring to ensure scalability and compliance with data protection regulations (GDPR, CCPA).

2. **Order & Request Fulfillment**
   - Coordinate with logistics partners to schedule and complete clothing pickups.
   - Process recycled items: sort, grade, and route to appropriate facilities (resell, refurbish, recycle).
   - Manage seller payouts and handle returns/exchanges.

3. **Data Analysis & Optimization**
   - Weekly reviews of key metrics: conversion rate (Add to Cart → Purchase), pickup adoption rate, detail-view rate on map.
   - Quarterly user surveys to gather qualitative feedback on pain points (e.g., “Was checkout too long?”).
   - Monthly sprint retrospectives to prioritize bug fixes and feature requests.

4. **Content & Inventory Management**
   - Curate second-hand item listings: ensure high-quality photos, accurate descriptions, and fair pricing.
   - Update environmental impact data as new reports become available.
   - Craft marketing copy for email campaigns, in-app banners, and social media posts.

## 8. Key Partners
- **Logistics Providers**
  - Local courier services for at-home pickups (e.g., GreenCourier, EcoPickup).
  - Bulk shipping partners to consolidate recycled textiles and send them to processing centers.

- **Recycling Centers & Charity Shops**
  - Regional drop-off locations (bins, community centers, charity-run stores).
  - Partner NGOs that process recycled textiles into new products (e.g., insulation, rags).

- **Payment Gateway**
  - Stripe or PayPal for secure payment processing.
  - PCI-compliance monitoring to ensure cardholder data safety.

- **Data Providers**
  - Environmental research organizations supplying up-to-date water and carbon footprint metrics.
  - Third-party services for address validation and postal lookup.

- **Marketing Affiliates & Influencers**
  - Collaborate with eco-bloggers, sustainable fashion influencers, and local community groups to drive awareness.
  - Affiliate program with bloggers earning a commission for each new user or sale generated.

## 9. Cost Structure

- **Development & Hosting (Minimal/Low-Cost)**
  - Use free or student-tier hosting options (e.g., GitHub Pages, Heroku free tier) for frontend; minimal or no server costs.
  - Rely on free/open-source mapping solutions (e.g., OpenStreetMap) instead of paid API licenses.

- **Logistics & Operations (Student-Run)**
  - Partner informally with local campus groups or community organizations to collect donated textiles (no courier fees).
  - Leverage on-campus storage space (e.g., student union closet) and volunteer labor for sorting and quality checks.

- **Data Licensing (Free/Public Sources)**
  - Use publicly available environmental datasets (e.g., government open data on water and carbon footprints).
  - Maintain a simple, manually updated benchmark table instead of paying for premium data services.

- **Marketing & Acquisition (Grassroots/Organic)**
  - Promote via student-run social media accounts and campus bulletin boards (no ad spend).
  - Collaborate with campus clubs or environmental student organizations for organic outreach.
  - Use free email tools included with student accounts (e.g., Gmail) for basic newsletters and updates.

- **Support & Staffing (Volunteer/Student Interns)**
  - Rely on project team members or student interns for customer support and operations coordination (no salaried staff).
  - Ask volunteers (e.g., fellow students) to create marketing materials, take item photos, and write copy.

# Minimum Viable Product (Initial Version)

## In Scope

### 1. Home Dashboard
- **Personalized Impact Metrics**  
  - **Water Saved**  
    - Displays cumulative liters of water saved by users who purchase second-hand or recycle items instead of buying new.  
    - Provides a breakdown by week and by month to illustrate usage trends over time.  
    - Tooltip details explain how water savings are estimated (e.g., average water required to produce a new garment minus water needed for processing recycled textiles).  
    - Users can click on a chart point to see a list of specific items contributing to that week’s/month’s savings.  
  - **Carbon Emissions Reduced**  
    - Shows cumulative CO₂e (carbon dioxide equivalent) savings since account creation—updated in real time as users log purchases or recycle items.  
    - A comparison widget highlights “Your total vs. average user in your city/region” to foster friendly competition.  
    - Per-item drill-down: clicking on the number reveals CO₂e saved per recycled or purchased item, with data sources cited (e.g., EPA, industry standards).  
    - If a user hovers over a particular bar on the bar chart, they see “Item X saved Y kg CO₂e,” plus a quick “Share” button for social media.  
  - **Items Recycled**  
    - Total count of articles of clothing or textiles recycled, with a filter by “drop-off” vs. “pickup.”  
    - Historical log: clicking “View History” opens a modal showing each recycled item’s name/description, date, drop-off location (or pickup date), and points earned.  
    - Milestone badges: once a user recycles 10 items, they unlock “Recycling Novice”; at 25 items, “Recycling Adept”; at 50 items, “Recycling Hero.” The badge appears on the profile.  
    - A progress bar below the “Items Recycled” count shows how many more items are needed to reach the next badge.  
- **Composite Sustainability Score**  
  - A single gauge (range 0–100) combining weighted metrics:  
    1. Water Saved (30% weight)  
    2. Carbon Reduced (40% weight)  
    3. Items Recycled (30% weight)  
  - Color-coded sectors on the gauge:  
    - **Red (0–30):** “Getting Started”  
    - **Orange (31–60):** “On Your Way”  
    - **Green (61–100):** “Sustainability Champion”  
  - If the user’s score increases by more than 5 points in a week, a confetti animation briefly appears with a “+” icon showing how many points were gained.  
  - Clicking on the gauge opens a breakdown modal explaining exactly how each component contributed to the current score.  
- **Interactive Charts**  
  - Toggle between **daily**, **weekly**, and **monthly** views for each metric (water, carbon, items) by selecting tabs above the chart area.  
  - A line chart for “Water Saved” and “Carbon Reduced” trends; a bar chart for “Items Recycled.”  
  - The chart is zoomable: users can click-and-drag to zoom into a particular time span.  
  - A legend at the bottom explains color coding (e.g., blue = water, green = carbon, purple = items).  
  - On mobile devices, the chart scrolls horizontally, allowing users to swipe through different weeks or months.  
- **Quick-Action Buttons**  
  - **Schedule a Pickup**  
    - Opens the pickup scheduler directly; if the user has no saved address, prompts them to add one.  
    - Shows next available time slots (today, tomorrow, next 7 days).  
    - If it’s within 24 hours of the chosen slot, button text turns red: “Last chance to book this slot!”  
  - **Find a Drop-off Location**  
    - Opens the interactive drop-off map centered on the user’s current or specified location.  
  - **Browse Current Sales**  
    - Takes users to the Sales Catalog, showing items on sale or newly added second-hand pieces.  
    - In the dashboard widget, shows a “Featured Item of the Day” thumbnail (clickable).  
  - All quick-action buttons display a small notification badge if there is an outstanding to-do:  
    - For instance, if the user has unredeemed rewards, a small “!” appears on “Rewards” icon in the top bar.  

---

### 2. Sales Catalog & Cart
- **Sales Page**  
  - **Filter Controls**  
    - Multi-select filters: gender, size, color, style, price range, and condition (e.g., “Like New,” “Good,” “Fair”).  
    - A slider for price range that updates the visible product grid in real time.  
    - “Sort By” dropdown: Relevance (default), Price: Low → High, Price: High → Low, Newest, Popular.  
  - **Search Bar with Autocomplete**  
    - Typing “jean” suggests “jean jacket,” “jean shorts,” etc., based on inventory.  
    - Displays recent searches underneath and trending keywords.  
  - **Product Cards**  
    - Each card displays:  
      1. Up to three thumbnail images (hover to cycle).  
      2. Item title (e.g., “Levi’s 501 Original Jeans”).  
      3. Price (e.g., “$24.99”).  
      4. Environmental footprint badge (e.g., “–10L water,” “–5kg CO₂e”).  
      5. Brand name and condition tag.  
    - Clicking on a card opens the **Product Detail View** (see below).  
  - **Pagination & Infinite Scroll**  
    - Default: show 20 items per page with “Load More” button at bottom.  
    - Option in settings: infinite scroll can be toggled on/off.  
- **Product Detail View**  
  - **High-Resolution Image Gallery**  
    - Main image larger; below it, a row of thumbnail previews.  
    - Clicking a thumbnail updates the main image.  
    - Zoom feature: hover over main image for a magnified view.  
  - **Product Details Section**  
    - Title, brand, size, color, material breakdown (e.g., 100% cotton).  
    - Environmental footprint badge showing water and carbon savings if the item is purchased.  
    - Condition description (e.g., “Minor cuff wear; overall excellent”).  
    - Seller information: username (anonymized), rating (stars), total items sold.  
  - **Pricing & Availability**  
    - Current price in bold (e.g., “$24.99”).  
    - “Add to Cart” button (primary color) plus “Add to Wishlist” (secondary).  
    - If inventory is low (≤ 2), show “Only 2 left!” in red under the price.  
    - Estimated shipping cost or free shipping threshold (e.g., “Free shipping for orders over $50”).  
  - **Related Items Carousel**  
    - A horizontal scroll showing 4–6 similar or complementary items (e.g., if user is viewing jeans, show tops or jackets).  
    - Each related item shows thumbnail, title, and price.  
- **Cart & Checkout**  
  - **Cart Summary**  
    - Lists all items currently in cart: thumbnail, title, size, quantity selector (1–5), price, “Remove” link.  
    - Subtotal, estimated shipping, tax, and total price are calculated in real time.  
    - “Continue Shopping” and “Proceed to Checkout” buttons at the bottom.  
  - **Checkout Form**  
    - **Step 1: Shipping Information**  
      - Pre-filled if user has saved address; else blank form fields for Name, Address, City, State, ZIP, Country.  
      - “Use a different shipping address” checkbox to allow gift purchases.  
    - **Step 2: Payment Information**  
      - Credit card form (Name on card, Card number, Expiry, CVV) with placeholder for Stripe integration.  
      - Billing address: same as shipping by default; if unchecked, show separate fields.  
    - **Step 3: Order Review**  
      - Display a summary of items, shipping info, payment method (masked card).  
      - “Edit” links next to each section to go back and modify.  
      - “Place Order” button in primary color.  
  - **Order Confirmation Page**  
    - Thank-you message (“Thank you for your purchase!”) plus order number.  
    - Summary of purchased items, shipping address, estimated delivery date range.  
    - “Track Order” button (links to tracking page once integrated).  
    - Below the summary, show “You earned X points from this purchase” with a link to “View Your Rewards.”  

---

### 3. Recycling Drop-off Map
- **Interactive Map**  
  - Based on a mapping API (e.g., Google Maps), with custom markers for each drop-off location.  
  - **Search Bar & Autocomplete**  
    - Users can enter an address, ZIP code, or landmark; suggestions appear as they type.  
    - Nearby drop-off points (within 5 km, 10 km, or custom radius) automatically load and cluster if too many in view.  
  - **Radius Filter Slider**  
    - Slider options: 5 km, 10 km, 20 km, 50 km. Adjusting slider updates visible markers in real time.  
    - Users can also click “Use My Current Location” (with geolocation prompt).  
  - **Map Pins & Clustering**  
    - Green pin: charity drop-off bin  
    - Blue pin: partnered recycling center  
    - Orange pin: textile repair shop that accepts reusable items  
    - If > 15 pins are close together, cluster icon shows number of locations; clicking a cluster zooms in.  
  - **Legend & Filter Toggle**  
    - A legend box explains pin colors/types.  
    - Checkboxes to toggle on/off certain categories (e.g., show/hide “Repair Shops”).  
- **Location Details Panel**  
  - When a user clicks a pin, a slide-in panel from the right displays:  
    - **Name & Address** (clickable link to open Google Maps for directions).  
    - **Opening Hours** (e.g., M–F: 9am–5pm; Sat: 10am–2pm; Sun: Closed).  
    - **Accepted Items** (e.g., “Clothes, Shoes, Bags, Textiles”).  
    - **Contact Info** (phone number or email if available).  
    - **Photos** (up to 3 images of the drop-off point).  
    - **Distance** (e.g., “2.3 km away”).  
    - **“Get Directions”** button that opens the user’s default maps app with pre-filled destination.  
    - **“Mark as Visited”** toggle: once marked, the pin turns grey to indicate it’s been used; updates user’s recycling history.  
- **List View Toggle**  
  - Above the map, a “List View” button shows all locations in a scrollable list sorted by distance.  
  - Each list item shows name, address, distance, and “Get Directions” link.  

---

### 4. Pickup Scheduler
- **Booking Calendar**  
  - **Flatpickr Date/Time Selector** showing available dates (today onwards) in a calendar view.  
  - On days with no available slots, date is disabled/grayed out.  
  - Clicking on a date reveals time slots for that date (e.g., 9:00–10:00am, 1:00–2:00pm).  
  - If a user attempts to book less than 2 hours before a slot, show a tooltip: “Booking must be made at least 2 hours in advance.”  
- **Pickup Form**  
  - **Pickup Address**  
    - Pre-filled from user profile; user can choose “Use a different address” to enter a new one.  
  - **Item List Uploader**  
    - Two options:  
      1. **Text List:** user types descriptions of items (e.g., “3 shirts, 2 pairs of jeans”).  
      2. **Photo Upload:** user can upload up to 5 photos of items (JPEG/PNG, ≤ 5MB each).  
    - Below the upload area, show guidelines: “Max 5 photos; each under 5MB; no videos.”  
  - **Special Instructions** field (optional) for notes like “Ring doorbell twice,” “Leave items on back porch,” etc.  
  - **Pickup Confirmation & Reminders**  
    - After submission, show a summary screen:  
      - Date & Time slot, Address, Item list (text or thumbnails of photos), Instructions.  
      - “Edit” link to modify before final confirmation.  
      - “Confirm Pickup” button.  
    - Once confirmed:  
      - Automated email and in-app notification is scheduled 24 hours before the slot: “Reminder: Your pickup is scheduled for [Date] at [Time].”  
      - If the user has not confirmed within 10 minutes of booking, send a follow-up email: “Please confirm your pickup details.”  

---

### 5. Profile & Account Hub
- **Profile Management**  
  - **Personal Information**  
    - View/Edit: First Name, Last Name, Email, Phone Number, Postal Address (street, city, state, ZIP, country).  
    - Option to upload/change avatar; shows circular preview once uploaded (max 2MB JPG/PNG).  
    - “Save Changes” button appears only when a field is modified.  
  - **Password Change**  
    - “Change Password” link opens a modal: Current Password, New Password (with strength meter), Confirm New Password.  
    - If the new password is weak, show “Use at least 8 characters, including numbers and symbols.”  
- **My Recycling**  
  - **Recycle History Log**  
    - A table with columns: Date, Method (Drop-off vs. Pickup), Item Type (e.g., “Shirt,” “Pants”), Location or Scheduled Slot, Points Earned.  
    - Pagination: 10 entries per page; “Load More” button at bottom.  
    - “Download History” button allows CSV export of recycled items.  
  - **Points & Rewards**  
    - Points balance meter graphic (e.g., “You have 150 points”).  
    - Below the meter, a list of unlocked badges (e.g., “Recycling Hero”).  
    - “How to Earn Points” section listing:  
      1. Recycle an item (10 points each)  
      2. Make a purchase (1 point per $1 spent)  
      3. Schedule & complete a pickup (15 points)  
      4. Refer a friend (50 points once they make first purchase).  
- **My Orders & Rewards**  
  - **Order History**  
    - List of past purchases: Order #, Date, Total Amount, Status (Delivered, In Transit, etc.).  
    - “View Details” expands to show items purchased, shipping address, tracking number (if available).  
  - **Available Coupons/Discounts**  
    - Grid of coupon cards. Each card shows:  
      - Coupon Code (e.g., “SAVE10”)  
      - Discount description (e.g., “10% off any order over $50”)  
      - Expiry date (e.g., “Expires: July 31, 2025”)  
      - “Redeem” button (disabled if already used or expired).  
    - Below the grid, “How to Redeem” explains the process (enter code at checkout).  
  - **Redemption History**  
    - Table showing past redemptions: Coupon Code, Description, Date Redeemed, Order # Applied To.  
- **Help & Support**  
  - **FAQ Section** (Accordion layout)  
    - Categories: Orders & Shipping, Recycling & Pickup, Points & Rewards, Payment & Billing, Account Settings.  
    - Each category expands to show 4–5 common Q&A items.  
  - **Contact Form**  
    - Fields: Subject (dropdown), Message (textarea, max 500 characters), Attachment upload (optional, for screenshots up to 2MB).  
    - “Submit” button—upon submission, show “Thank you! Our support team will get back to you within 24 hours.”  
  - **Live Chat Placeholder**  
    - A banner at the bottom-right: “Live Chat (Coming Soon)”—clicking opens a modal with “We’re launching live chat in July 2025! Meanwhile, send us a message via the contact form.”  

---

## Out of Scope (for Future Iterations)
- Any rental-related features (completely removed).  
- Premium subscription tier implementation (planned for a later version).  
- Advanced analytics dashboard for admins.  
- Integration with third-party loyalty programs.  

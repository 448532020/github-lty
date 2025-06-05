# Minimum Viable Product (Medium Detail)

## 1. Home Dashboard
- **Impact Overview**  
  - **Water Saved**: Shows cumulative liters saved by choosing second-hand purchases or recycling, with a simple line chart for weekly/monthly trends.  
  - **Carbon Reduced**: Displays total CO₂e savings since signup, updated in real time.  
  - **Items Recycled**: Total count of recycled items, with badges unlocked at 10, 25, and 50 items.  
- **Composite Score**  
  - Single “Sustainability Index” (0–100) combining water, carbon, and recycled counts. Color-coded gauge:  
    - Red (0–30): Getting Started  
    - Orange (31–60): On Your Way  
    - Green (61–100): Champion  
- **Quick Actions**  
  - **Schedule a Pickup**: Opens the pickup scheduler and shows next available slots.  
  - **Find a Drop-off Location**: Launches the interactive map centered on the user’s location.  
  - **Browse Sales**: Navigates to the Sales Catalog where users can shop second-hand items.

---

## 2. Sales Catalog & Cart
- **Sales Page**  
  - **Filters**: Gender, size, price, and condition (“Like New,” “Good,” “Fair”).  
  - **Search**: Autocomplete suggestions for item names and styles.  
  - **Product Cards**: Thumbnail, title, price, and environmental footprint badge. Clicking opens product details.  
- **Product Detail View**  
  - **Image Gallery**: Main photo with thumbnail previews and zoom-on-hover.  
  - **Details**: Title, brand, size, material, and condition description.  
  - **Footprint Badge**: Shows estimated water and carbon savings if purchased.  
  - **CTA Buttons**: “Add to Cart” (primary) and “Add to Wishlist” (secondary).  
  - **Related Items**: A horizontal carousel of similar listings.  
- **Cart & Checkout**  
  - **Cart Summary**: List of selected items (thumbnail, title, quantity, price), with subtotal, estimated shipping, and total.  
  - **Checkout Flow**:  
    1. **Shipping Info**: Pre-filled if available; editable fields for address.  
    2. **Payment Info**: Credit card form (placeholder for Stripe).  
    3. **Order Review**: Summary of items, shipping, and payment method; “Place Order” button.  
  - **Confirmation**: Thank‐you message with order number, estimated delivery range, and “You earned X points” note.

---

## 3. Recycling Drop-off Map
- **Interactive Map**  
  - **Search Bar**: Enter address or ZIP; autocomplete suggestions.  
  - **Radius Filter**: Slider for 5 km, 10 km, or 20 km. Clicking “Use Current Location” recenters the map.  
  - **Pins & Clustering**:  
    - Green pins for charity bins, blue pins for recycling centers, orange pins for repair shops.  
    - Clusters display a count when many locations overlap; clicking a cluster zooms in.  
  - **Legend & Filters**: Toggle visibility of each location type.  
- **Location Details Panel** (opens on pin click)  
  - Name, address, opening hours, accepted items list, and distance.  
  - “Get Directions” link opens the user’s default map app.  
  - “Mark as Visited” checkbox: once checked, pin fades to grey and the action is logged in recycle history.  
- **List View Toggle**: Shows locations in a scrollable list sorted by distance, each with a “Get Directions” link.

---

## 4. Pickup Scheduler
- **Date/Time Selection**  
  - **Flatpickr Calendar**: Displays available dates starting from today; disabled greyed-out days have no slots.  
  - **Time Slots**: When a date is selected, available morning/afternoon slots appear below (e.g., 9–10 AM, 2–3 PM). Slots less than 2 hours out are disabled.  
- **Pickup Request Form**  
  - **Pickup Address**: Pre-filled from profile; option to enter a different address.  
  - **Item Input**:  
    - **Text List**: User types “3 shirts, 2 pants,” etc.  
    - **Photo Upload**: Up to 5 images (JPEG/PNG, ≤ 5 MB each).  
  - **Special Instructions**: Optional notes (e.g., “Leave on porch,” “Call upon arrival”).  
  - **Confirmation Screen**: Summary of date, time, address, and item list with “Edit” or “Confirm Pickup” buttons.  
  - **Reminders**: Automated email/app notification 24 hours before the scheduled pickup.

---

## 5. Profile & Account Hub
- **Profile Management**  
  - View and edit personal information: name, email, phone, and address.  
  - Upload or change avatar (max 2 MB JPG/PNG).  
  - “Change Password” modal with current and new password fields (with strength indicator).  
- **My Recycling**  
  - **History Log**: Table with Date, Method (drop-off/pickup), Item Type, Location or Slot, and Points Earned.  
  - **Points Balance**: Displays current points; “How to Earn” section lists actions (recycle item = 10 points, purchase = 1 point/$1, complete pickup = 15 points, refer friend = 50 points).  
  - **Export History**: “Download CSV” button for personal use.  
- **My Orders & Rewards**  
  - **Order History**: List of past purchases with Order #, date, total, and status. “View Details” shows item breakdown and shipping info.  
  - **Available Coupons**: Grid of coupon cards showing code, discount details, expiry date, and “Redeem” button.  
  - **Redemption History**: Table with Coupon Code, Description, Date Redeemed, and Order # used.  
- **Help & Support**  
  - **FAQ Section**: Accordion with categories (Orders, Recycling, Pickup, Points, Account).  
  - **Contact Form**: Subject dropdown, message textarea (max 500 chars), optional attachment upload (≤ 2 MB). “Submit” shows a thank-you confirmation.  
  - **Live Chat Placeholder**: Banner/link “Live Chat (Coming Soon)”.

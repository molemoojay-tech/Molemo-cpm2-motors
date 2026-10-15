# Molemo CPM2 Motors — Working Local MVP

This is a browser-based starter website for the Molemo CPM2 Motors marketplace.

## Open and test
1. Extract the ZIP file.
2. Open `index.html` in Chrome, Edge, Firefox, or another modern browser.
3. Internet is needed for the remote demonstration car photos. The core storefront works without a build step.
4. Browse the shop, add products to cart, apply `MOLEMO10`, place a demo guest order, then track the order using the generated `MCM-XXXXXX` reference.
5. Open **Admin** in the footer and use the demo code `DEMO2026` to test product, order and discount management.

## What works in this local MVP
- Responsive black-and-gold storefront.
- Product search, categories and sorting.
- Cart quantities, removal, subtotal and demo discount codes.
- Guest checkout creates a demo order and tracking reference.
- Local order tracking.
- Customer order lookup by email (local demo only).
- Admin demo for adding/hiding/deleting products, updating demo order status, manually changing a demo payment label, and managing discount codes.
- Sales report counters based on local demo data.
- WhatsApp support links, after configuration.

## IMPORTANT — not ready for real customers or real payments
This version stores data in the browser's `localStorage`. It is not shared between users/devices and can be edited or erased by a visitor. The demo admin code is visible in the source. There is no secure authentication, shared database, payment gateway, email service, or verified EFT workflow. Do not publish this version as a live store or collect real customer data with it.

## Configure WhatsApp
Open `index.html`, find this line near the bottom of the script:
`const number=localStorage.getItem('mcm_whatsapp')||'';`
Replace the empty fallback with your business WhatsApp number in international digits only, without `+` or spaces, for example `27XXXXXXXXX`. Do not use someone else's number without permission.

## Recommended production next step
Build a production backend using a service such as Supabase:
- Database tables: `products`, `profiles`, `orders`, `order_items`, `discount_codes`, `payment_events`.
- Enable row-level security; customers must only read their own orders.
- Admin roles must be checked server-side, not just hidden in the frontend.
- Use Supabase Auth for customer sign-in and password reset.
- Store product images in a managed storage bucket.
- Use a legitimate payment provider's official integration and verify payment webhooks server-side.
- Manual EFT orders must remain pending until a person verifies the funds in the bank account; never trust a screenshot alone.
- Deploy over HTTPS and set a custom domain only after testing.
- Add privacy, terms, delivery and refund policies and verify the game's rules for each type of digital good.

## CPM2 / digital goods note
This is an independent fan-made concept and is not affiliated with the game's publisher. Verify the current game rules before listing accounts or services. Account listings are not enabled in this starter.

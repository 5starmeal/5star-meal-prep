# 5STARMEALS — Vercel deployment starter

## Publish
1. Upload the **contents of this folder** (not the outer folder or zip) to the root of your private GitHub repository.
2. In Vercel choose Add New > Project > Import your GitHub repository `5starmeal/5star-meal-prep`. Set Framework Preset to **Other**; output directory `public` (also in vercel.json). Deploy.
3. In Vercel Project > Settings > Environment Variables, set `STRIPE_SECRET_KEY` to your **Stripe test-mode secret key**. Never put it in GitHub or chat. Optionally set `PUBLIC_URL` to your actual `https://...vercel.app` address. Redeploy.
4. Test an 8-meal order and a 20-meal order with Stripe test mode, including 48-hour pickup validation and the success page.
5. Before accepting live payments, switch to the live Stripe key, add reliable merchant notifications and a fulfillment dashboard, test end-to-end, confirm sales tax, refunds, privacy and allergen procedures.

## Features
- 8–20 meals, $12 for 8–19 and $10 for 20; prices are validated server-side.
- 1 protein, 1 rice, 1–3 vegetables, 1 side, 1 sauce per combination.
- Pickup daily 12–8 PM Eastern at 703 N Shore Drive, Jeffersonville IN 47130, minimum 48 hours after checkout.
- Stripe hosted checkout, and payment status verification on return.
- Stripe session metadata contains the full order JSON split into `order_00`, `order_01`, etc. Reassemble keys in numerical order to view order details in Stripe Dashboard.

## Important launch limitations
This is a **deployment-ready test/staging starter, not a finished production ordering system**. There is no order database, automatic merchant email, admin order management, capacity limits, or Stripe webhook fulfillment integration. Stripe metadata is an interim way to retain order selections; add durable database storage, webhook processing, and operational notifications before live orders. Customer pickup time is selected before payment, so the 48-hour buffer is calculated when checkout starts; long-abandoned checkout sessions should be expired/revalidated before fulfillment. There is no automated tax calculation. Verify kitchen licensing, insurance, allergy policy and local rules.

The file `public/brand-logo.png` contains the selected logo artwork, but the header currently uses text; artwork can be incorporated in a later design pass.

# Mistvale assessment notes

## 1. What I changed
- Reworked the one-page store into a responsive, mobile-first tea shop while keeping the project as one `index.html` with inline CSS and JavaScript.
- Removed the old framework/icon dependencies and rebuilt interactions with plain HTML, CSS and JavaScript.
- Fixed product filtering, category state, sorting, search race conditions, quick view, wishlist state, cart quantities, remove-item behavior, cart counts, price calculation, coupon logic, shipping logic, delivery checking and checkout submission.
- Prices and stock are always read from `PRODUCTS`; cart records store product IDs and quantities rather than copied page prices.
- Implemented the stated cart rules: maximum 5 packs per product and never above stock, sold-out products last in every sort, WELCOME10 case-insensitivity, ₹399 coupon minimum, 10% eligible-item discount capped at ₹150, gift-box exclusion, ₹49 shipping and free shipping after discount at ₹599.
- Added accessible labels, focus states, keyboard-friendly controls, Escape-to-close overlays, reduced-motion support and inline form feedback.
- Added the required FAQ and FAQPage structured data, Organization/Product structured data, canonical/description/social metadata and meaningful image alt text.
- Kept the approved footer legal wording unchanged.
- Added a saved wishlist as a small bonus feature.

## 2. What the AI got wrong / what I caught
The supplied page contained several issues that were deliberately checked rather than trusted: it used jQuery, Font Awesome and animate.css despite the no-library rule; category matching was case-sensitive; search used a truthy `indexOf()` test that could include the wrong products; fast/slow searches could overwrite each other; quick-view image handlers captured the wrong loop index; cart prices were read from rendered text instead of `PRODUCTS`; quantity arithmetic could concatenate strings; the remove function could delete multiple items; cart count counted lines instead of units; the coupon could be stacked repeatedly and was not capped or restricted to eligible items; gift boxes could receive the discount; shipping was calculated from the wrong threshold and before discount; delivery checking had no rejection handler; and checkout was only an alert instead of submitting the required contract form.

The original page also contained unsupported or contradictory marketing copy, including an expired 2025 Diwali countdown and claims that were not supported by `BRAND.md`. I removed the unsupported campaign/countdown instead of inventing a new sale date. The original announcement said free shipping above ₹499 while the existing shipping calculation used ₹599; because the brief did not state the numeric threshold, I retained ₹599 as the temporary working threshold and documented the decision here.

## 3. Images
The supplied PNGs were placeholder-style graphics with inconsistent aspect ratios and large file sizes. I replaced them with a consistent 1:1 Mistvale visual system and a lightweight hero asset, plus an SVG wordmark. The assets were rendered locally as simple tea-pack illustrations using the supplied brand palette, then converted to WebP for web delivery. Product images are about 10 KB each and the hero is about 15 KB; all are comfortably below the brief's size limits.

## 4. How I tested it
- Checked the final JavaScript with Node syntax validation.
- Inspected the final HTML structure and required form contract.
- Checked image dimensions and file sizes.
- Verified the legal footer wording was retained.
- Checked the implementation against the README rules, especially cart maths, stock limits, coupon eligibility/cap, shipping-after-discount, search/filter/sort state, API usage and checkout fields.
- Intended manual browser checks: desktop and 360px/390px mobile widths, keyboard navigation, cart add/increase/decrease/remove, coupon edge cases, delivery valid/invalid/unserviceable pincodes and checkout payload.

## 5. Questions for the team
- The brief says shipping becomes free at a “free-shipping threshold” but does not state the numeric value. The original code used ₹599 while its announcement used ₹499. I used ₹599 and called out the discrepancy rather than silently guessing.
- The supplied page contained a 2025 Diwali countdown, but no current campaign end date was provided. I removed it rather than inventing a new campaign.

## 6. Time spent
Approximately 4 hours including reading the brief, implementation, asset preparation and checks.

## 7. Extra features
- Persistent wishlist using local storage.
- Quick-view modal with keyboard/Escape support.
- Persistent, cleaned cart state across reloads.
- Search request protection against stale asynchronous results.

## 8. With more time I would…
I would run a full Lighthouse pass in Chrome, test with a screen reader, add automated browser tests for every business-rule edge case, and confirm the free-shipping threshold with the team before launch.

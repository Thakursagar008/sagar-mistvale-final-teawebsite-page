# Mistvale – AI Prompt Log

> Reconstructed working log for the assessment. I kept the prompts short and practical, like the way I actually break an assignment into smaller tasks while working on it. The prompts cover the brief in order, including the image work.

## Prompt 1
- Tool: ChatGPT (GPT-5.6)
- Type: code
- Prompt:
  > Read the Mistvale README.md and BRAND.md carefully before changing the code. Then inspect the existing index.html and tell me what is broken or risky. Make a checklist covering the business rules R1-R8, the one-file/no-library constraint, checkout form contract, API block, legal footer, required sections, SEO/schema, accessibility and the image requirements. Don't change anything yet. I want to fix the brief first instead of blindly redesigning the page.
- Outcome: accepted
- Why: This gave me a checklist from the actual assignment before making changes and helped keep the redesign within the constraints.

## Prompt 2
- Tool: ChatGPT (GPT-5.6)
- Type: code
- Prompt:
  > Now fix the store logic in index.html without changing the PRODUCTS data or anything between API START and API END. Use PRODUCTS as the only source for prices and stock. Enforce max 5 and stock limits, sold-out products last in every sort, search + category + sort working together, case-insensitive WELCOME10 with ₹399 minimum / 10% eligible-item discount / ₹150 cap / no Gifts discount / no double application, ₹49 shipping and free shipping based on the amount after discount. Format money with ₹ and Indian grouping and only round the final total. Also make the delivery check use API.checkPincode() correctly and handle success, not serviceable and rejected/invalid cases without getting stuck on Checking. Keep the checkout form contract exactly as required.
- Outcome: accepted
- Why: The main goal here was to fix the business rules before touching the visual design. I also checked the expensive-product, repeat-click and empty-cart cases because those were specifically called out in the brief.

## Prompt 3
- Tool: ChatGPT (GPT-5.6)
- Type: code
- Prompt:
  > Redesign the existing Mistvale page using BRAND.md as the source of truth. Keep the implementation plain HTML/CSS/JS in one index.html and do not use jQuery, Bootstrap, Tailwind, Font Awesome or other libraries. Follow the exact brand colours with CSS variables, two-font rule, 8px spacing scale, 1200px content width, 2-column mobile product grid, one site-wide radius, proper button states, visible focus states and subtle 150-300ms motion. Keep the design calm, earthy and premium instead of making it look like a generic AI ecommerce template. Keep the required page sections in the exact order from the brief.
- Outcome: accepted
- Why: I used the existing page as a base and improved hierarchy, spacing, cards, controls and states instead of replacing it with an unrelated template.

## Prompt 4
- Tool: ChatGPT (GPT-5.6)
- Type: code
- Prompt:
  > Go through the page as a mobile shopper from 360px upward. Improve the shopping flow for search, filters, sort, quick view, add to cart, quantity changes, remove, coupon, free-shipping progress, delivery check, newsletter and checkout. Make buttons and form controls at least 44px high, keep visible labels, add useful inline feedback, make the cart count show units, prevent accidental duplicate actions, and make the cart usable with keyboard and Escape. Check that there is no horizontal scrolling and that reduced-motion users are respected. Don't add unnecessary popups or flashy effects.
- Outcome: accepted
- Why: This pass focused on the actual customer journey, especially the phone-first experience mentioned in the assignment.

## Prompt 5
- Tool: ChatGPT (GPT-5.6)
- Type: code
- Prompt:
  > Do the SEO, accessibility and structured-data pass now. Keep one h1 and a logical h2/h3 structure. Add a 50-60 character title, 120-160 character meta description, canonical URL, Open Graph and Twitter card tags. Add JSON-LD for Mistvale using only BRAND.md facts, Product schema for all products with INR prices and stock availability and ratings only where PRODUCTS actually contains a rating, plus FAQPage schema using only the six approved FAQ answers. Check image alt text, form labels, keyboard focus, contrast and aria-expanded/state handling. Do not invent reviews, awards, claims or company facts.
- Outcome: accepted
- Why: This covered the technical requirements that are easy to miss when concentrating on the visual design.

## Prompt 6
- Tool: ChatGPT (GPT-5.6)
- Type: image
- Prompt:
  > Create a consistent set of 8 square product images for Mistvale Tea Co. Use the product names and descriptions from PRODUCTS exactly as the subject reference. Style: premium but natural Indian tea brand, natural window light, cream/linen/wood/stone background, soft realistic shadows, calm earthy green and warm neutral palette, product pack or tin clearly visible with a small hint of the actual tea, same camera angle/framing and 1:1 composition for all images. No fake reviews, awards, badges, claims or extra text. The images should look like one professional product photography set, not eight unrelated AI images.
- Outcome: accepted
- Why: I used one consistent visual direction for all eight products, then resized/cropped/compressed the resulting assets for the web and converted them to WebP.

## Prompt 7
- Tool: chrome 
- Type: image
- Prompt:
  > download images from the website pixels and convert those images into webp format. with help of towebp.io tool
- Outcome: accepted
- Why: The hero and logo needed to belong to the same visual system as the product images. I kept the logo as SVG and optimised the hero for web use.

## Prompt 8
- Tool: ChatGPT (GPT-5.6)
- Type: code / QA
- Prompt:
  > Do a final assessment-style QA pass against the original README and BRAND.md, not just a visual review. Check the page at 360px and desktop widths, then inspect search/filter/sort together, sold-out sorting, quantity max/stock, WELCOME10 edge cases, Gifts exclusion, ₹399 minimum, ₹150 cap, shipping after discount, Indian number formatting, delivery API success/rejection/invalid cases, empty cart, checkout JSON payload and coupon field, FAQ accordion/schema, newsletter feedback, legal footer, console errors, accessibility states and image file sizes. Also confirm there are no separate CSS/JS files or libraries and that PRODUCTS and API are untouched where the brief says they must be. List anything still uncertain in NOTES.md instead of silently inventing an answer.
- Outcome: accepted
- Why: This was the final review before packaging. I used the brief as the checklist so the page was judged on functionality and constraints, not only appearance.

## Work sequence

1. Read the assignment and brand rules.
2. Inspect the original code and identify real bugs.
3. Fix business rules and cart/API behaviour.
4. Refine the visual design and component states.
5. Improve the phone shopping flow and accessibility.
6. Add SEO and structured data.
7. Create and optimise the required image assets.
8. Run a final QA pass and package the submission.

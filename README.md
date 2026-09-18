# Whimsy Vine Creations — website

Plain HTML/CSS, no build step, no framework. Free to host on Cloudflare Pages.

## Files

- `index.html` — Home / landing page
- `story.html` — Story / about page
- `events.html` — Upcoming Events list
- `store.html` — Store (product grid + Square Buy Buttons)
- `css/style.css` — all styling for every page

## Preview it right now

You don't need a server for this — just double-click `index.html` (or any page) and it opens in your browser. Click around the nav to check all four pages and try shrinking the window to see the mobile layout.

## What's placeholder vs. real

Every spot that needs real content is marked `[PLACEHOLDER: ...]` in the page text, and photo spots are dashed boxes that say `[PLACEHOLDER PHOTO]`. Search each file for "PLACEHOLDER" to find every one. Nothing will look broken without real photos — the placeholder boxes are intentional so you can see exactly what's missing.

## How to add a new event

Open `events.html`, find the comment block that says `EVENT CARD TEMPLATE`, copy one whole `<div class="event-card">...</div>` block, paste it in date order, and fill in the month, day, event name, location, and time. Delete a card once that event has passed.

## How to add a new store item

Open `store.html`, find the comment block that says `PRODUCT CARD TEMPLATE`, copy one whole `<div class="product-card">...</div>` block, and:

1. Swap the `photo-placeholder` div for a real `<img src="images/your-photo.jpg" alt="...">` once you have a product photo. (Roughly 800x800px square photos work best for the grid.)
2. Set the badge class to `badge-original` for one-of-a-kind paintings, or `badge-print` for anything repeatable (prints, cards, pumpkins).
3. In your Square dashboard, go to **Payment Links** (or **Buy Button**), create a checkout link for that exact item, and paste the embed code Square gives you in place of the `buy-button-slot` div.
4. For one-of-a-kind originals, set the item's inventory quantity to **1** in Square so it automatically shows sold out online the moment it sells anywhere (online or at a market). It won't stop an in-person double-sale by itself — a quick glance at the Square app before re-selling a one-off piece at a market is still worth the habit.

## Adding real photos

Create an `images/` folder next to `index.html`, drop your photos in there, and reference them as `images/filename.jpg` in an `<img>` tag. Keep photos under ~500KB each (export at web quality, not full camera resolution) so pages load fast.

## Deploying

1. Push this whole folder to your GitHub repo.
2. In the Cloudflare dashboard, go to **Workers & Pages > Create > Pages > Connect to Git**, pick this repo, and leave the build settings blank (no build command, no output directory needed — it's already static).
3. Once it deploys, go to the Pages project's **Custom domains** tab and add whimsyvinecreations.com. Since the domain is already in the same Cloudflare account, DNS should connect in one click.

## Updating the live site later

Any time you edit a file and push the change to GitHub, Cloudflare Pages automatically rebuilds and republishes within a minute or two — nothing else to do.

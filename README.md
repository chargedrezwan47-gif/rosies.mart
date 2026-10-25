# rosies.mart

A mobile-first online order page for a small beauty shop. Customers pick a
product, choose color, size and quantity, enter their name, phone number and
address, and the order is sent to the shop owner on WhatsApp.

Single file, no build step, no dependencies.

## Features

- Mobile-only layout (a fixed phone-width column)
- Dark / light toggle, live product search
- Product popup with color, size and quantity
- Order tab with name, phone and address
- One-tap "Send order on WhatsApp" with the full order pre-written
- Scroll animations, breathing-glow logo (respects "reduce motion")

## Quick start

1. Open `index.html` in a text editor.
2. Edit the block marked `EDIT THIS SECTION` near the top of the script:
   - `SHOP.whatsapp` — your WhatsApp number with country code, no `+` or spaces
     (for example `8801XXXXXXXXX`). **Orders cannot be sent without it.**
   - `SHOP.name` and `SHOP.currency`
   - `SEED` — your product list. Each product has `name`, `price`, `image`
     (a file path, URL or `data:` URI), optional `colors` and `sizes` lists,
     and an `order` number for sorting.
3. Open the file in a browser to test, then place a test order.

## Deploy (free)

Upload `index.html` to any static host: GitHub Pages, Netlify Drop,
Cloudflare Pages, and so on. Share the resulting link with customers.

## How orders reach you

The page has no server. When a customer presses "Place order", it opens a
`wa.me` link with the order text. The customer must press Send in WhatsApp,
so an order is not final until that message arrives. If you need orders saved
automatically or online payments, you will need a backend service.

## Claude-hosted version

When opened inside claude.ai as an artifact, the same page also provides an
owner panel (add/delete products, upload photos, view saved orders). Those
features only work there and are skipped when the file is hosted elsewhere.

## Fonts

Loaded from Google Fonts: Patrick Hand and Cormorant Garamond. The page falls
back to system fonts when offline.

## License

MIT — see [LICENSE](LICENSE). Replace the copyright holder with your own name.

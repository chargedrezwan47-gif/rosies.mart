[README.md](https://github.com/user-attachments/files/33923363/README.md)
# rosies.mart

A mobile-first online order page for a small beauty shop. Customers pick a
product, choose color, size and quantity, enter their name, phone number and
address, and the order is sent to the shop owner on WhatsApp.

Single file, no build step, no dependencies.

## Features

- Mobile-only layout (a fixed phone-width column)
- Dark / light toggle, live product search
- Product names and prices shown under each picture
- Product popup with color, size and quantity, with "Add to cart" (keep shopping) and "Order now"
- Cart bar at the bottom showing item count and total
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

## Admin login and owner panel (optional, Supabase)

1. Create a free project at supabase.com.
2. Open `setup.sql`, replace `YOUR_ADMIN_EMAIL` with your email, paste it into
   Supabase > SQL Editor and run it.
3. Supabase > Authentication > Users > Add user: enter that same email and a
   strong password (tick "Auto confirm user"). Then, in Authentication
   settings, turn off new user sign-ups.
4. Supabase > Project Settings > API: copy the Project URL and the anon /
   publishable key into `SUPA={url:"",key:""}` in `index.html`.
5. Open your site, tap "Admin login", sign in. If the shop is empty, the 6 sample
   products are imported automatically; edit them or add your own. Orders are saved there and also sent to WhatsApp.

The anon key is safe to publish; the security rules in `setup.sql` let only
your admin email change data. Never put the `service_role` key in the page.

## Claude-hosted version

When opened inside claude.ai as an artifact, the same page also provides an
owner panel (add/delete products, upload photos, view saved orders). Those
features only work there and are skipped when the file is hosted elsewhere.

## Fonts

Loaded from Google Fonts: Patrick Hand and Cormorant Garamond. The page falls
back to system fonts when offline.

## License

MIT — see [LICENSE](LICENSE). Replace the copyright holder with your own name.

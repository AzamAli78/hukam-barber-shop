# Shop site template — WhatsApp booking

A one-page website for a local shop. Single HTML file, no build step, no database,
no server. Every "book" button opens WhatsApp with the message already typed.

`index.html` is a sample for a fictional barber shop (Hukam Hair Studio) used as a
demo. Copy it per client and change the parts listed below.

## Deploy

**GitHub Pages** — push this folder to a repo, then Settings → Pages → Source:
`Deploy from a branch` → branch `main`, folder `/ (root)` → Save. Live in about a
minute at `https://<username>.github.io/<repo>/`.

**Netlify Drop** — go to [netlify.com/drop](https://app.netlify.com/drop) and drag
this folder in. Instant link, no account needed to start.

Both are free. A custom domain (`shopname.in`) can be pointed at either one later.

## Customise for a client

Everything you need to change is text in `index.html`. Search and replace:

| Find | Replace with |
| --- | --- |
| `919876543210` | client's WhatsApp number, country code first, no `+` or spaces |
| `98765 43210` | the same number, formatted for display |
| `Hukam Hair Studio` | shop name |
| `Men's Salon · Phagwara` | what they do and where |
| `Cut · Shave · Grooming` | their tagline |

Then edit by hand:

- **Services** — the `<ul class="menu">` block. Each `<li>` is one service: name,
  price, one line of detail, and its own WhatsApp link. Change the `text=` part of
  each link so the message matches the service.
- **Timings** — the `.hours` block. Indian salons usually close Tuesday; check.
- **Address** — the `.addr` paragraph, and the `query=` in the Google Maps link.
- **Why us** — the three `.feat` boxes. Use real things about the shop, not filler.
- **Preview image** — `og.png` is what shows when the link is shared on WhatsApp.
  Remake it at 1200×630 with the client's name, or delete the `og:image` tag.
  **After deploying, change `og:image` to the full URL** (`https://.../og.png`);
  WhatsApp usually ignores a relative path, and the preview comes out blank.

## Colours

All colours are tokens at the top of the `<style>` block. Change these five and the
whole page follows:

```
--ink      page background
--ink-2    cards and bars
--cream    main text
--brass    accent (headings, prices, links)
--wa       WhatsApp green — leave this alone
```

## What this template does not do

No online booking, no payments, no customer database, no login. Enquiries go to
WhatsApp and the shop replies by hand. Say this clearly to the client before taking
money, so nobody expects a booking system.

# Soma Swasthya — Setup Guide

Your website is one file: `index.html`. You don't need to install anything to preview it — just double-click it and it opens in your browser. The steps below take it from "preview on my computer" to "live on the internet, taking bookings and payments," using only free tools.

## 1. Add your logo

1. Save your logo as `logo.png` in the same folder as `index.html`.
2. Open `index.html` in a text editor (Notepad, TextEdit, or similar).
3. Find the comment that says `LOGO GOES HERE` near the top.
4. Replace the SVG code block just below it with:
   ```
   <img src="logo.png" alt="Soma Swasthya logo" class="brand-mark">
   ```

## 2. Add your photo

Find `about-portrait` further down and replace the placeholder text block with:
```
<img src="avanthi.jpg" alt="Avanthi Singh">
```
(Save your photo as `avanthi.jpg` in the same folder.)

## 3. Set up free booking (Calendly)

1. Go to **calendly.com** and create a free account.
2. Create an "Event Type" for each session length you offer (e.g. Initial Consultation, Follow-Up).
3. Click **Share → Add to Website → Inline Embed**, and copy the code Calendly gives you.
4. In `index.html`, find the comment `CALENDLY EMBED GOES HERE` and paste Calendly's code in place of the placeholder block described there.

The free Calendly plan supports **one event type**; if you want several (Initial, Follow-Up, etc. each with their own calendar), you can either link each "Book This" button on a Service card straight to a separate free Setmore or Calendly page — no embed required, just change the `link` field for that service to the booking URL.

## 4. Set up free payments (Stripe)

1. Go to **stripe.com** and create a free account (no monthly fee — Stripe takes a small % only when you actually get paid).
2. Go to **Payment Links** in your Stripe dashboard and create one link per product or service (set the price, currency, and product name).
3. Stripe automatically detects and accepts payment in the customer's local currency for most cards.
4. In `index.html`, find `const PRODUCTS` (for shop items) or the `link` field inside `const SERVICES` (for paid consultations), and paste your Stripe Payment Link into `stripeLink` or `link`.

## 5. Add or edit services and products

This content lives in a separate file, `data.json`, not in `index.html` itself — so day-to-day changes never touch the site's code. Once your site is live on GitHub Pages, see **EDITING-GUIDE.md** for a full walkthrough of editing `data.json` directly in your browser (no software needed).

## 6. Publish the site for free

Pick one:

**Option A — GitHub Pages (recommended, fully free forever)**
1. Create a free account at **github.com**.
2. Create a new repository, and upload these files: `index.html`, `data.json`, `logo.png` (and your photo, once added).
3. Go to the repository's **Settings → Pages**, set the source to your main branch, and save.
4. GitHub gives you a live link like `yourname.github.io/soma-swasthya` within a few minutes.

Once live, see **EDITING-GUIDE.md** — you'll be able to add services, products, and prices straight from GitHub's website whenever you like.

**Option B — Cloudflare Pages (also free forever)**
1. Create a free account at **pages.cloudflare.com**.
2. Upload your folder directly (drag-and-drop, no coding required).
3. Cloudflare gives you a live link immediately, and lets you connect a custom domain later for free.

## 7. (Optional) Use your own domain name

A domain name like `somaswasthya.com` is the one part of this stack that isn't free (typically $10–15/year from a registrar like Namecheap or Google Domains). Everything else in this guide — hosting, booking, and payments — remains free regardless of whether you use a custom domain or the free one GitHub/Cloudflare gives you.

---

**Questions or want help with any of these steps?** Just come back and ask — I can walk through Calendly setup, Stripe Payment Links, or hosting in more detail whenever you're ready.

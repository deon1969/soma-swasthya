# Editing Your Site — No Software Needed

Once your site is live on GitHub Pages (see SETUP-GUIDE.md, step 6), you can add or change services, products, and prices entirely from your web browser — no downloads, no code editor, no command line. This is your "backdoor," and you never need to come back and ask for a content change again.

## The one file you'll touch: `data.json`

Everything that changes often — services, products, prices, descriptions — lives in one file called `data.json`. The website's design and layout live in a separate file (`index.html`) that you should never need to open.

## How to edit it

1. Go to your repository on **github.com** (the one you created in Setup step 6).
2. Click on **`data.json`** in the file list.
3. Click the **pencil icon** (✏️) in the top-right of the file view — this opens GitHub's built-in text editor, right in your browser.
4. Make your change (see examples below).
5. Scroll down, add a short note like "Added new product" in the commit box, and click **Commit changes**.
6. Wait about 30–60 seconds — your live site updates automatically. No further steps.

That's it. No app to install, no server to touch.

## Example: adding a new product

Find the `"products"` section. Each product looks like this:

```json
{
  "name": "Tridosha Balancing Tea",
  "description": "A gentle daily tea formulated to suit all three constitutions.",
  "price": "$21",
  "stripeLink": "#contact"
}
```

To add a new one, click right after the `}` that closes the last product, type a comma, then paste in a new block with your own text:

```json
,
{
  "name": "Neem Detox Capsules",
  "description": "Gentle daily support for clear skin and healthy digestion.",
  "price": "$26",
  "stripeLink": "#contact"
}
```

## Example: adding a new service

Same idea, under `"services"`:

```json
,
{
  "name": "Panchakarma Prep Session",
  "duration": "45 min",
  "description": "A guided session to prepare your body and routine ahead of a panchakarma cleanse.",
  "price": "$95",
  "icon": "leaf",
  "link": "#booking"
}
```

Available icons: `"leaf"`, `"root"`, `"compass"`, `"box"` — pick whichever fits, or reuse one from an existing entry.

## Example: changing a price

Find the item, and just change the text inside the quotes:

```json
"price": "$24"
```
becomes
```json
"price": "$28"
```

## A couple of things that matter

- **Commas matter.** Every entry except the very last one in a list needs a comma after its closing `}`. If you get an error or the site looks broken after a change, it's almost always a missing or extra comma — GitHub's editor will usually underline the problem in red.
- **Keep the quotation marks** around text — `"name": "New Product"`, not `name: New Product`.
- **Preview before committing:** GitHub's editor has a "Preview" tab that shows if the file is still valid JSON before you commit.
- If you ever break something, GitHub keeps full history — open the file, click **History**, and you can see or restore any earlier version.

## When you'd still need my help

- Changing the site's design, colors, or layout (that lives in `index.html`, not `data.json`)
- Connecting Calendly or Stripe for the first time
- Anything involving actual code, not just content

Day-to-day content — new offerings, price changes, descriptions — you can now do entirely yourself, whenever you like.

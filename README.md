# iat-home

The landing page that houses every IAT tool. It is the front door of the
[IAT Portal ecosystem](../docs/00-ecosystem-overview.md): a single page that
links out to each in-house app and is ready to grow as we ship more.

## What it is

- A **single, self-contained `index.html`** — plain HTML, CSS, and JavaScript,
  no framework and no build step (the same approach as `iat-ticketing`).
- Matches the IAT design language (Inter font, brand green `#089447`, light/dark
  theme toggle, rounded cards) without copying the forms or ticketing layouts.
- Fully responsive and accessible; respects the OS dark-mode preference and
  remembers a manual override per browser.

## Adding an app

Open `index.html` and add an entry to the `APPS` array near the bottom of the
file. Nothing else needs to change — the card renders automatically.

```js
{
  title: 'IAT Learn',
  href: 'https://iat-learn.vercel.app',
  desc: 'Short, plain-English description of the tool.',
  status: 'live',          // 'live' = clickable, 'soon' = dimmed placeholder
  accent: '#8b5cf6',       // icon tile / hover colour
  tags: ['Training'],      // small pills under the description
  icon: '<path d="..."/>'  // inline SVG (24×24 viewBox, stroke style)
}
```

## Linked apps

| App                | URL                                  | Status |
|--------------------|--------------------------------------|--------|
| Forms Portal       | `https://iat-forms-portal.vercel.app`| Live   |
| Support Ticketing  | `https://iat-ticketing.vercel.app`   | Live   |

> **Note:** update the `Forms Portal` URL in `index.html` if the main portal
> uses a custom domain rather than its `*.vercel.app` address.

## Running & deploying

- **Locally:** open `index.html` in a browser, or serve the folder
  (`npx serve .`).
- **Vercel:** deploy this folder as a static project (no framework preset).
  `vercel.json` enables clean URLs.

_Part of the IAT Portal. See [`../docs`](../docs) for the full system manual._

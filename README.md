# Rhombus Accessories & BOM Builder

Single-page tool for building a Rhombus Bill of Materials: pick a device
(camera / access control / sensor / relay), storage, and mount type; see the
required accessories; and assemble an exportable BOM (Copy / Share link / CSV /
PDF / Print).

Everything lives in **`index.html`** — no build step, no dependencies to
install. Fonts (Sora / DM Sans) load from Google Fonts and product images load
from `rhombus.com` at runtime.

## Live deployments

| Host | URL |
|------|-----|
| GitHub Pages | https://rhombussystems.github.io/rhombus-accessories/ |
| Vercel (Rhombus team) | `accessoriesbom.rhmbs.app` *(after import — see below)* |

The **Terrain: Tool Hub** button auto-hides on the Vercel-served copies
(`*.vercel.app` / `*.rhmbs.app`) and shows only on GitHub Pages.

## Deploy to Vercel (Rhombus team)

DNS for `rhmbs.app` is managed **inside Vercel** (nameservers
`ns1/ns2.vercel-dns.com`), so attaching a subdomain needs **no registrar step** —
Vercel auto-creates the record and issues SSL.

### 1. Import the repo

1. [vercel.com](https://vercel.com) → switch to the **Rhombus** team.
2. **Add New → Project** → import `RhombusSystems/rhombus-accessories`.
   (The Vercel↔GitHub app is already installed on the org, so no new auth.)
3. Settings during import:
   - **Framework Preset:** `Other`
   - **Root Directory:** `./`
   - **Build Command:** *(empty / override off)*
   - **Output Directory:** *(empty / override off)*
   - **Install Command:** *(empty / override off)*
   - **Environment Variables:** none
4. **Deploy.**

### 2. Add the custom domain

1. Project → Settings → **Domains** → add `accessoriesbom.rhmbs.app`.
2. Vercel auto-verifies (zone is on the same team) and issues SSL — live in ~1 min.
3. Optional: mark it **Primary** and redirect the generated `*.vercel.app` URL to it.

Both GitHub Pages and Vercel redeploy automatically on every push to `main`.

## Files

| File | Purpose |
|------|---------|
| `index.html` | The entire app (markup, styles, data, logic). |
| `vercel.json` | Static-serve config: clean URLs, no-cache on `index.html`, security headers. |
| `README.md` | This file. |

## Branding

Uses the Rhombus design tokens from rhombus.com — dark teal `#17323b`, cyan
`#00c1de` / `#4bebff`, CTA blue `#0057ff`, Sora (headings) + DM Sans (body), and
the Rhombus diamond mark in the header.

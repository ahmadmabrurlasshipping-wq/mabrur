# Cloudflare setup guide for this project

## 1) Which Cloudflare product fits this repo?

This repository is currently a **static single-page HTML application** with browser `localStorage` persistence.

Recommended path:
1. **Cloudflare Pages** (best fit now): static hosting + global CDN + simple deploys.
2. **Cloudflare Workers** (optional later): add API endpoints (auth, server-side validation, email triggers, webhooks).
3. **Cloudflare D1 / R2 / KV** (optional later): move from browser-only storage to shared persistence.

## 2) Prerequisites

- Node.js 18+
- A Cloudflare account

Install Wrangler globally or use `npx`:

```bash
npm install -g wrangler
# or
npx wrangler --version
```

## 3) Authenticate Wrangler

```bash
wrangler login
```

This opens a browser and links your CLI to your Cloudflare account.

## 4) Deploy to Cloudflare Pages

This repo is already configured with `wrangler.toml` and `pages_build_output_dir = "."`.

Run:

```bash
npx wrangler pages deploy . --project-name las-fleet-monitoring
```

If the project does not exist yet, Wrangler creates it automatically.

## 5) Inspect Pages project via Wrangler

```bash
npx wrangler pages project list
npx wrangler pages deployment list --project-name las-fleet-monitoring
```

## 6) Use Cloudflare MCP for inspection/deploy

If your MCP environment exposes a Cloudflare server/plugin, you can:

1. List available MCP resources/tools.
2. Select the Cloudflare project resource.
3. Inspect deployments/logs or trigger deploy actions from MCP.

In this workspace session, MCP resource discovery returned no configured resources/templates, so Cloudflare MCP actions were not available yet.

## 7) Suggested next step for production hardening

- Add Cloudflare Access in front of the app because this is an internal operational tool.
- Add a custom domain and enforce HTTPS.
- Add CI deployment from GitHub via Pages build settings.

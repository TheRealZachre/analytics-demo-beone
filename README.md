# Analytics Demo BeOne

Standalone social media analytics and reporting demo for BeOne, with a built-in Platform Admin Console for user management.

## Local development

```bash
npm install
cp .dev.vars.example .dev.vars   # add AUTH_SECRET
npm run dev
```

Open http://localhost:3001

## Admin console

Admins see **Platform Admin** in the sidebar (`/admin`) — same user-management console as the main Digital Dashboard app. This demo uses its own user database (`data/demo-users.json` / KV on Cloudflare).

## Deploy to Cloudflare

### Git-connected Workers Builds

| Setting | Value |
|---------|--------|
| **Build command** | `npm run build` |
| **Deploy command** | `npx wrangler deploy` |

Add **AUTH_SECRET** under Worker → Settings → Variables and Secrets.

Worker name: `analytics-demo-beone`

### Manual deploy

```bash
npm run deploy
```

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

### GitHub Actions (alternative to dashboard Git integration)

This repo includes `.github/workflows/deploy-cloudflare.yml`. Add these secrets under GitHub → Settings → Secrets and variables → Actions:

| Secret | Value |
|--------|--------|
| `CLOUDFLARE_API_TOKEN` | Cloudflare API token with Workers Scripts:Edit |
| `CLOUDFLARE_ACCOUNT_ID` | `a56999249f230e52c5856d42eaee5f33` |
| `AUTH_SECRET` | Same secret used for NextAuth |

Every push to `main` builds and deploys automatically.

### Manual deploy

```bash
npm run deploy
```

# ZriCloud product site — zricloud.com

Files: `index.html` (product page), `login.html` (sign-in placeholder), `styles.css`, `assets/` (logo, favicons).

## Host it free on Cloudflare Pages, using the GoDaddy domain

### 1. Upload the site (about 5 minutes)
1. Create a free account at dash.cloudflare.com.
2. Go to **Workers & Pages → Create → Pages → Upload assets**.
3. Project name: `zricloud`. Upload the contents of this folder (index.html must be at the top level).
4. The site goes live at `https://zricloud.pages.dev`. Open it and check it.

### 2. Connect zricloud.com (recommended way: move DNS to Cloudflare, free)
1. In Cloudflare: **Add a domain → zricloud.com → Free plan**. Cloudflare shows two nameservers (e.g. `xxx.ns.cloudflare.com`).
2. In GoDaddy: **My Products → zricloud.com → DNS → Nameservers → Change → "I'll use my own nameservers"** and enter the two Cloudflare nameservers. Save.
3. Wait for Cloudflare to show the domain as **Active** (usually under an hour, at most 24–48 hours).
4. In Cloudflare: **Workers & Pages → zricloud → Custom domains → Set up a domain** → add `zricloud.com`, then again for `www.zricloud.com`. Cloudflare creates the DNS records and the HTTPS certificate.

Note: if you later set up email on zricloud.com, add its MX records in Cloudflare DNS, not GoDaddy, once the nameservers are moved.

### Alternative: keep DNS at GoDaddy
In GoDaddy DNS, add a CNAME record `www` → `zricloud.pages.dev`, then add `www.zricloud.com` as a custom domain in Cloudflare Pages. Use GoDaddy's **Forwarding** to send `zricloud.com` to `https://www.zricloud.com`. This works, but the first option is cleaner.

## Before giving the URL to DIC
- `login.html` is a placeholder. It sends nothing anywhere. When the ZriCloud console is attached, replace the form with a link or redirect to the live console (for example `https://app.zricloud.com`).
- To update the site later: Cloudflare Pages → zricloud → **Create new deployment** → upload the changed folder.

# Deploy to GitHub Pages — step-by-step

The local repo is already initialized, all files staged, and an initial
commit made. You need to push it to GitHub, then enable Pages in the
repo settings.

## 1. Create the GitHub repo

Go to <https://github.com/new>:

- **Owner**: `princessamygdala`
- **Repository name**: `social-learning-review` (matches what's in the README)
- **Public** (required for GitHub Pages on free tier)
- **Do NOT** check "Add a README" — we already have one
- **Do NOT** check "Add .gitignore" — we already have one
- Click **Create repository**

## 2. Push from this directory

GitHub will show a "…or push an existing repository from the command
line" snippet. Use these commands (run from this folder):

```bash
cd /Users/md1864/Desktop/review_extraction_03-19-26/social-learning-review-public
git remote add origin https://github.com/princessamygdala/social-learning-review.git
git push -u origin main
```

The push will be ~280 MB and may take 2–5 minutes depending on your
internet connection.

If you'd rather use SSH (no password prompt each time), substitute:

```bash
git remote add origin git@github.com:princessamygdala/social-learning-review.git
```

## 3. Enable GitHub Pages

After the push completes:

1. Open the repo on GitHub: <https://github.com/princessamygdala/social-learning-review>
2. Click **Settings** (top nav)
3. Click **Pages** in the left sidebar
4. Under **Source**, pick **Deploy from a branch**
5. Branch: **main** · Folder: **/ (root)** · Save
6. Wait ~1–2 minutes for the first deploy

A green banner will appear at the top of the Pages settings showing the
live URL:

> **Your site is live at https://princessamygdala.github.io/social-learning-review/**

The URL is also shown by GitHub at the top of the Pages section after
the deploy completes.

## 4. Share the link

Once live:

- Test the link in a fresh browser window (not the one logged into GitHub)
  to make sure it loads without auth.
- Hard-refresh the first visit so the brain map iframes load.
- Share via email / Slack / paper draft / lab page.

## Troubleshooting

**Push asks for username/password.**
GitHub no longer accepts password auth on HTTPS. Use a **personal
access token** (Settings → Developer settings → Personal access tokens
→ generate a token with `repo` scope; paste it as the password) OR
switch the remote to SSH (Step 2 alt).

**Push is rejected because GitHub thinks the repo isn't empty.**
You probably checked one of "Add README" / ".gitignore" / "license"
when creating. Either delete the repo and re-create empty, or run
`git pull origin main --allow-unrelated-histories` first then push.

**Pages shows 404 after enabling.**
Wait 2–3 minutes — first deploy can be slow. Then hard-refresh.
If still 404, check that **Source = main / root** and not a different
branch.

**Page loads but brain maps show blank iframes.**
Mixed-content blocks. The site loads CDN libraries over HTTPS; if any
asset is HTTP-only, browsers strip it. The current build only uses
HTTPS CDNs, so this shouldn't happen — but if it does, open the
browser console and look for "Mixed Content" warnings.

**280 MB feels too big.**
GitHub allows 1 GB recommended / 5 GB hard limit on a free repo, so
you're fine. GitHub Pages serves files individually, so a visitor only
downloads the files they actively click on (typically 8.6 MB for the
main page + 2.5 MB for each brain view they open).

## Updating the site later

When you re-run analyses and want to update the live site:

```bash
cd /Users/md1864/Desktop/review_extraction_03-19-26/social-learning-review-public
# Re-copy fresh files from writeups/review_website/
# (or add a script that does this)
git add -A
git commit -m "Update snapshot to YYYY-MM-DD"
git push
```

Pages re-deploys automatically within ~1 minute.

## Custom domain (optional, later)

If you buy a domain (e.g. `socialcompreview.org`):

1. Settings → Pages → Custom domain → enter the domain → Save.
2. At your domain registrar, add a CNAME record pointing
   `socialcompreview.org` to `princessamygdala.github.io`.
3. Wait 10–60 min for DNS propagation. GitHub will issue a free TLS
   certificate automatically.

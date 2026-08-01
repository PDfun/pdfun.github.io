# Pikus Squeeze

Your own link shortener. Unlimited, free, and every short link lives on **your own** github.io domain — no tinyurl, no third party.

## How it works
- `index.html` — the shortening tool. You connect it to your GitHub repo once (username, repo name, a personal access token), then every link you create gets written into `links.json` in your repo.
- `links.json` — the database. Just a flat file of `{ "code": "https://destination..." }`.
- `go.html` — the redirect page. When someone visits `yourdomain/go.html#code`, it looks up the code in `links.json` and redirects them instantly.

No server, no database service, no monthly cost — GitHub is the backend.

## One-time setup

### 1. Create a personal access token
Go to **github.com/settings/tokens?type=beta** → **Generate new token**:
- Repository access: **Only select repositories** → pick `pikus-squeeze`
- Permissions → **Contents**: set to **Read and write**
- Generate, then copy the token (starts with `github_pat_...`) — you won't see it again.

### 2. Connect the site
Open your deployed site, click the ⚙ icon top right, and enter:
- Your GitHub username
- Repo name (`pikus-squeeze`)
- Branch (`main`)
- The token you just created

Click **Save connection**. That's it — this is stored only in your browser.

### 3. Shorten away
Paste a link, hit Shorten. It writes straight to your repo and gives you back a link like:
```
https://yourusername.github.io/pikus-squeeze/go.html#a1b2c3
```

## Want the shortest possible links?
Name your repo exactly `yourusername.github.io` (GitHub's special "user site" repo name) — Pages then serves it at the root of your domain, so links become:
```
https://yourusername.github.io/go.html#a1b2c3
```

## Deploy to GitHub Pages
See the full walkthrough in chat, or:
1. Create a repo named `pikus-squeeze` (or `yourusername.github.io` for the shortest links).
2. Upload `index.html`, `go.html`, and `links.json`.
3. Settings → Pages → Deploy from branch → `main` / root → Save.
4. Live in a minute or two.

## Notes
- New links can take a few seconds to resolve after creation (GitHub's raw file cache) — refresh once if a brand-new link says "hasn't propagated yet."
- Your token stays in your browser's local storage only, and is sent only to `api.github.com`. Don't share your device/browser profile with anyone you don't trust with that token.
- History shown on the page is a local convenience list; the real source of truth is `links.json` in your repo.

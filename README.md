# Pikus Squeeze

A free, unlimited link shortener. No sign-up, no daily cap. Paste a long URL, get a short one back, and every link you create is saved in your browser's history for next time.

## Live demo
Once deployed to GitHub Pages, your site will be live at:

```
https://YOUR-GITHUB-USERNAME.github.io/pikus-squeeze/
```

## How it works
- The page is a single static file (`index.html`) — no server, no database, no backend needed.
- When you shorten a link, the page calls a public shortening service (CleanURI, with TinyURL and is.gd as backups) to generate a real, working short URL that anyone can click.
- Your link history is saved in your browser's local storage, so it stays with you on that device/browser only.

## Run it locally
Just open `index.html` in any browser — double-click it, no install needed.

## Deploy to GitHub Pages
See the full steps in the chat, or:
1. Create a new GitHub repo named `pikus-squeeze`.
2. Upload `index.html` (and this `README.md`) to it.
3. Go to **Settings → Pages**, set source to the `main` branch, root folder, and save.
4. Your site goes live at `https://YOUR-GITHUB-USERNAME.github.io/pikus-squeeze/` within a minute or two.

# June Moment Countdown

Embeddable countdown to June 11, 2026, 9:00 AM ET, Times Center NYC. One HTML file, no dependencies, works inside Notion via `/embed`.

## Preview it locally first

Double-click `index.html` in Finder. It opens in your default browser and should show roughly 50 days remaining.

To verify the T-0 state before you ship, open browser devtools (Cmd+Opt+I in Chrome), paste this in the Console tab, then wait 5 seconds:

```
(function(){ var t = Date.now() + 5000; setInterval(function(){ /* no-op, TARGET already closed over */ }, 1000); })();
```

Easier alternative: edit the `TARGET` line in `index.html` temporarily to `new Date(Date.now() + 5000)`, reload, watch the flip, then revert.

## Ship to GitHub Pages

1. Go to https://github.com/new. Sign in (or create an account, free).
2. Repo name: `june-moment-countdown`. Set to **Public**. Skip README/gitignore/license. Click **Create repository**.
3. On the new repo page, click **uploading an existing file**. Drag `index.html` from this folder. Leave the commit message as-is. Click **Commit changes**.
4. Go to **Settings** (top nav) → **Pages** (left sidebar).
5. Under **Build and deployment**, set **Source** to `Deploy from a branch`. Set **Branch** to `main`, folder `/ (root)`. Click **Save**.
6. Wait 30 to 60 seconds, then refresh the Pages page. You will see: `Your site is live at https://<your-username>.github.io/june-moment-countdown/`. Copy that URL.

## Embed in Notion

1. Open the Notion page where you want the countdown.
2. Type `/embed`, hit enter, paste the URL, press **Embed link** (not Bookmark).
3. Drag the corners to resize. Works at any width.
4. Repeat on every Notion page where you want it. One URL, many embeds.

## Making changes later

Edit `index.html` in the GitHub web UI (pencil icon), commit. GitHub Pages redeploys in about a minute. The Notion embed picks up the new version on the next page load.

Common edits:

- Change the target time: line with `TARGET = new Date("2026-06-11T09:00:00-04:00")`
- Change the copy: the `<section id="countdown">` and `<section id="live">` blocks
- Change the style: top of the file, inside `<style>...</style>`

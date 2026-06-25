# Knockout Cup — Web

A 32-team knockout football tournament you play in the browser. Pick a nation,
play a 60-second match, win or you're out, all the way from the Round of 32 to
the Final.

This folder is the complete website. It's plain static files, no build step, no
server code, which means it's free and trivial to host.

## Files

- `index.html` — the landing page (front door, explains the game, links to play).
- `play.html` — the game itself.
- `favicon.svg` — the little icon shown in the browser tab.
- `og-image.png` — the preview image shown when the link is shared on social media.

## Try it locally first

Just open `index.html` in your browser by double-clicking it. The whole site
works straight from your computer, no server needed. Click "Enter the tournament"
to make sure it hands off to the game.

(If you want to mimic a real server locally, from this folder run
`python3 -m http.server` and visit `http://localhost:8000`.)

## Put it online (pick one — all free)

You don't need to choose carefully; any of these works and all are free for a
site this size. Listed easiest-first.

### Option A — Netlify Drop (no account math, ~30 seconds)
1. Go to https://app.netlify.com/drop
2. Drag this whole folder onto the page.
3. It gives you a live URL instantly (e.g. `your-site.netlify.app`). Share it.
   To use your own domain later, you can add it in the site settings.

### Option B — GitHub Pages (best if you'll keep editing)
1. Create a free GitHub account and a new repository.
2. Upload these files to it (drag-and-drop in the web UI is fine).
3. In the repo: Settings → Pages → Source: "Deploy from a branch" → main → `/root`.
4. After a minute your site is live at
   `https://your-username.github.io/your-repo/`.
   This pairs nicely with editing in Cursor: commit a change, it redeploys itself.

### Option C — Cloudflare Pages or Vercel
Both let you connect a GitHub repo (or drag a folder) and give a free URL with
fast global hosting. Good if you expect a lot of players.

## Custom domain (optional)

Once it's live on any of the above, you can point a domain you own (like
`knockoutcup.com`) at it from that host's dashboard. Each host has a short guide;
search "<host name> custom domain".

## Making the share preview work

When someone pastes your link into WhatsApp, X, Discord, etc., they'll see the
`og-image.png` card with the title and description. Two things to know:
- The `og:image` path is relative, so it works once everything is hosted together.
  If your preview doesn't show, make sure `og-image.png` is in the same folder as
  `index.html` on the host.
- Some platforms cache previews. If you change the image, use the platform's
  debugger (e.g. Facebook Sharing Debugger) to refresh it.

## Editing later (in Cursor or any editor)

- Change wording, colours, or the layout in `index.html`.
- The game logic all lives in `play.html`. Match length, difficulty, teams, and
  controls are all in the `<script>` near the bottom.
- The colour identity (pitch green, lime accent) is set as CSS variables at the
  top of each file's `<style>`; change them in one place to re-skin everything.

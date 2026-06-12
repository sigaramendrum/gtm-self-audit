# GTM Self-Audit — Sigaram Endrum

A single-page, branded, self-scoring Go-to-Market audit (Planning & People) to accompany the keynote *"Go-to-Market: The New Differentiator in the AI Era."* No build step, no backend — it's one `index.html`. All answers are computed in the visitor's browser and saved only to their own `localStorage`; nothing is sent to a server.

This is a **draft template with seeded questions** — designed so you can flesh it out (more questions, more lenses, more detail) by editing one config block.

## Run it locally
Just open `index.html` in any browser. (Or, for a local server: `python3 -m http.server` in this folder, then visit `http://localhost:8000`.)

## Publish on GitHub Pages
1. Create a new GitHub repo (e.g. `gtm-self-audit`) and add these files to the root.
2. Repo **Settings → Pages → Build and deployment → Source: "Deploy from a branch"**, branch `main`, folder `/ (root)`. Save.
3. After a minute it's live at `https://<your-user>.github.io/gtm-self-audit/`.
4. Optional custom domain: add a `CNAME` file with e.g. `audit.sigaramendrum.com` and point a DNS CNAME at `<your-user>.github.io`. Set it in **Settings → Pages → Custom domain**.

Once it's live, send me the URL and I'll regenerate the conference QR code to point at the site instead of the Google Doc.

## Edit the questions (the part you'll iterate on)
Open `index.html`, find the **`AUDIT` config block** near the top of the `<script>` (it's clearly marked). Everything is plain data:

- **Add a question** → add a string to a lens's `q: [ ... ]` array.
- **Add a lens** → add `{ name, desc, q:[ ... ] }` to a section's `lenses` array.
- **Add a section** → add a new object to `sections` (give it a unique `id`).
- **Change wording / archetypes / Monday-morning text / footer** → edit the corresponding fields.

Scoring is **percentage-based**, so adding or removing questions just works — you never touch the maths or the score bands. The "three or more *No*s = unowned" flag is automatic per section.

## Branding
Colours and fonts are set in the `:root` CSS variables and the Google Fonts link at the top — they match the deck palette (charcoal `#0E1116`, warm white `#F5F2EC`, gold `#C8A45C`, teal `#3B6E8F`). To add a logo, drop an `<img>` into the `.brand` element in the top bar.

## Files
- `index.html` — the whole app (markup + styles + logic + questions).
- `README.md` — this file.

---
*Draft v1 · Sigaram Endrum LDA*

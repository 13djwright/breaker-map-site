# Breaker Map — Marketing & Legal Site

Static HTML/CSS site that hosts the public-facing pages required for
the Breaker Map iOS App Store submission:

- `index.html` — Marketing landing page
- `privacy.html` — Privacy Policy (required by App Store Connect)
- `support.html` — Support / FAQ (required by App Store Connect)
- `style.css` — Shared styling, light + dark mode aware
- `assets/` — App icon imagery used across pages

No build step. Plain HTML and CSS served straight from GitHub Pages.

## Publishing with GitHub Pages

1. **Create a new repository** on GitHub. Suggested name:
   `breaker-map-site` (used in the URL below — adjust if you pick
   something else). Make it public.

2. **Add the remote and push** from this directory:

   ```bash
   cd "/Users/devinwright/Development/Breaker Map Site"
   git remote add origin git@github.com:devinwright/breaker-map-site.git
   git push -u origin main
   ```

3. **Enable GitHub Pages**:
   - Repository → Settings → Pages
   - **Source**: Deploy from a branch
   - **Branch**: `main` / `/ (root)`
   - Save.

4. **Live URL** appears within a minute or two. With the suggested repo
   name it will be:

   ```
   https://devinwright.github.io/breaker-map-site/
   ```

   With pages reachable at:

   - Marketing: `https://devinwright.github.io/breaker-map-site/`
   - Privacy:   `https://devinwright.github.io/breaker-map-site/privacy.html`
   - Support:   `https://devinwright.github.io/breaker-map-site/support.html`

5. **Update the iOS app**: in the Breaker Map repo, edit
   `BreakerMap/App/AppLinks.swift` to point at the three URLs above.
   Then update the same URLs in App Store Connect under App
   Information.

## Before going live — required edits

- [ ] **Contact email**. Every page currently uses
  `support@breakermap.app` as a placeholder. Pick one of:

  - Register the `breakermap.app` domain (or `.dev`, `.io`, etc.) and
    set up email forwarding to your real inbox.
  - Create a dedicated Gmail address such as
    `breakermap.support@gmail.com` and search-replace
    `support@breakermap.app` in all three HTML files.
  - Use any other personal address you're comfortable having public.

  Whatever you pick must be reachable. App Review will email it.

- [ ] **Confirm GitHub handle**. The instructions above assume your
  handle is `devinwright`. If it's different, adjust the remote URL
  in step 2 and the live URL throughout.

- [ ] **Confirm repo name**. Defaults to `breaker-map-site`. If you
  name the repo differently, the `/breaker-map-site/` path segment
  in the published URL changes accordingly.

- [ ] **Pro launch claim** (optional). The landing page currently
  says "Coming soon to the App Store." Swap this for an App Store
  badge once the app is approved.

## Custom domain (optional, post-launch)

If you register a domain later (e.g. `breakermap.app`), point a CNAME
record at `devinwright.github.io` and add a `CNAME` file to this repo
containing the domain. GitHub Pages will serve from your domain over
HTTPS automatically.

## Editing

It's a plain static site. Edit the HTML files in any text editor,
commit, push. The change goes live within a minute or two.

Light/dark mode follows the visitor's system preference via CSS
`prefers-color-scheme` — no JavaScript required.

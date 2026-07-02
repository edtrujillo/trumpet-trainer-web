# Trumpet Trainer — website

Static marketing site + **Privacy Policy** and **Support** pages for the Trumpet
Trainer app. Plain HTML/CSS, no build step, no dependencies.

```
index.html      Landing page (features, plans, store badges)
privacy.html    Privacy Policy  ← the URL the app stores require
support.html    Support / FAQ / contact
styles.css      Shared brass/cream theme
```

## Before publishing — fill the placeholders

Search for and replace these across `index.html`, `privacy.html`, `support.html`:

- `[DATE]` — the privacy policy's effective date
- `[ContactPlus / your legal name]` / `[ContactPlus]` — your legal/business name
- `support@contactplus.com` — your real support + data-request email
- `[mailing address ...]` — optional postal address (or remove)
- Store badge links: replace the two `href="#"` buttons in `index.html` with your
  real App Store / Google Play URLs (and, ideally, the official badge images).
- (Optional) uncomment the video section in `index.html` and add your YouTube embed.

## Preview locally

No build needed — just open `index.html`, or serve the folder:

```bash
python3 -m http.server 8000   # then visit http://localhost:8000
```

## Create the repo & push

```bash
git init -b main
git add .
git commit -m "Trumpet Trainer website"
gh repo create contactplus/trumpet-trainer-web --public --source=. --push
```

## Deploy (pick one)

- **Cloudflare Pages / Netlify / Vercel** (recommended): connect the GitHub repo,
  set the build command to *none* and the output/publish directory to the repo
  root (`/`). Auto-deploys on every push; free HTTPS; easy custom domains; works
  with private repos.
- **GitHub Pages**: repo **Settings → Pages** → Deploy from branch → `main` / root.
  (Free Pages requires a public repo.)

## Custom domain → the store URLs

Point a subdomain (e.g. `trumpettrainer.contactplus.com`) at your host via a DNS
CNAME, enable HTTPS, then use these exact URLs:

- **Privacy Policy** — `https://<your-domain>/privacy.html`
  - App Store Connect → App Privacy → **Privacy Policy URL**
  - Play Console → App content → **Privacy policy**
- **Support** — `https://<your-domain>/support.html` (Play/App Store **Support URL**)

> Keep the privacy policy here as the single published source of truth so it never
> drifts from what you paste into the stores.

# Tide — website

Static site for **tide.zenkolabs.com**. No build step, no framework, no lock-in.
Just HTML + one CSS file. Hosted free on GitHub Pages.

## Layout

```
tide-site/
├── index.html              Landing page (hero, philosophy, rhythm, story)
├── privacy.html            Privacy Policy
├── terms.html              Terms of Service
├── medical-disclaimer.html Medical Disclaimer
├── delete-account.html     Account deletion instructions
├── support.html            Support / contact
├── 404.html                Not-found page
├── CNAME                   GitHub Pages custom domain
├── README.md               This file
└── assets/
    └── styles.css          Shared design system
```

## Files

| File | Purpose | Launch status |
|---|---|---|
| `index.html` | Landing page (hero, philosophy, rhythm, story) | Polish later |
| `privacy.html` | Privacy Policy | **🚩 LAUNCH BLOCKER** — App Store + Play Store require this URL |
| `terms.html` | Terms of Service | Needed before Tide+ (v2.0); fine to ship now |
| `medical-disclaimer.html` | Medical Disclaimer | Linked from Terms; ship with v1 |
| `delete-account.html` | Account deletion instructions | **🚩 LAUNCH BLOCKER** — Apple Guideline 5.1.1(v) |
| `support.html` | Support / contact | **🚩 LAUNCH BLOCKER** — App Store Connect requires a support URL |
| `404.html` | Not-found page | Nice-to-have |
| `assets/styles.css` | Shared design system | — |
| `CNAME` | Tells GitHub Pages to serve at `tide.zenkolabs.com` | Required for custom domain |

## Deploy (one-time, ~10 min)

1. Create a new GitHub repository (e.g. `tide-site`) under your account.
2. Upload every file in this folder to the repo root (including `CNAME`).
3. Repo → **Settings → Pages** → Source: `Deploy from a branch` → Branch: `main` / `(root)` → Save.
4. In your DNS provider for `zenkolabs.com`, add a **CNAME record**:
   - Host/Name: `tide`
   - Value: `<your-github-username>.github.io`
5. Back in **Settings → Pages**, confirm the custom domain shows `tide.zenkolabs.com` and tick **Enforce HTTPS** once it's available (can take up to ~24h for the cert).

That's it. The site is live and owned entirely by you — no Carrd, no monthly fee.

## Updating later

- Edit any `.html` file directly on GitHub (pencil icon) or locally and push.
- Changes go live in ~1 minute. No rebuild needed.
- The site is portable: these same files run as-is on Netlify, Cloudflare Pages, or any static host if you ever move.

## ⚠️ Before you submit to the App Store — fill in every placeholder

Search the project for `[` to find them all. At minimum, replace:

- `[LEGAL ENTITY NAME]` — the legal entity that operates Tide
- `[JURISDICTION]` / `[GOVERNING LAW JURISDICTION]` — where you're based / governing law
- `[PRIVACY CONTACT EMAIL]` and `[SUPPORT CONTACT EMAIL]` — real, monitored addresses
- `[EFFECTIVE DATE]` / `[DATE]` — dates on Privacy & Terms
- `[DATA REGION]` — Supabase hosting region
- `[MINIMUM AGE]` / `[13 / 16 ...]` — age thresholds per jurisdiction
- `[X] days` / `[X] business days` — your real deletion + support response windows
- Confirm the **analytics/diagnostics section of `privacy.html`** matches exactly what ships in v1.0 and your App Store privacy "nutrition" labels.
- Replace the **founder story placeholder** in `index.html` with your real words.

> Not legal advice: these documents are solid, Tide-specific starting drafts, but a
> health-data app should have the Privacy Policy and Terms reviewed by a
> qualified professional before launch.

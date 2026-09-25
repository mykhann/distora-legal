# Distora legal pages

Static pages your app already links to (`ProfileScreen.tsx` opens `.../privacy.html`), plus the
account-deletion page Google Play's Data Safety form requires. No build step, no subfolders —
same flat layout as the other repo (`index.html`, `privacy.html`, `delete-account.html` at root).

```
index.html            landing / links to the other two
privacy.html          privacy policy
delete-account.html   how to delete your account + what's deleted vs. kept
```

## Before you publish

Both `privacy.html` and `delete-account.html` have `[BRACKETED]` placeholders — search for `[` and
fill in every one:
- `[LEGAL ENTITY NAME]` / address — who legally operates Distora
- `[SUPPORT EMAIL]` — an inbox you actually check
- `[DATE]` — when the policy takes effect
- `[X] business days` — how long a manual (email) deletion request takes you

Have the privacy policy reviewed by someone qualified for your users' jurisdictions (GDPR if you
have EU/UK users, CCPA for California, etc.) — it's written to accurately describe what the app
does, but it isn't legal advice.

There's no `terms.html` here since one wasn't requested — either write one or remove that link
from all three pages and from `ProfileScreen.tsx`.

## Publish with GitHub Pages

1. Push these files to the root of a repo (e.g. `distora-legal`, same pattern as `heckle-legal`).
2. **Settings → Pages → Source: Deploy from a branch → Branch: `main` → Folder: `/ (root)`**.
3. Your URLs will be:
   `https://<your-username>.github.io/<repo-name>/privacy.html`
   `https://<your-username>.github.io/<repo-name>/delete-account.html`

   Want a custom domain (e.g. `distora.app/privacy.html`) instead? Add a file named `CNAME`
   containing just the domain, set it under **Settings → Pages → Custom domain**, and point your
   registrar's DNS at GitHub Pages (GitHub's docs list the current A records to use).
4. Visit both pages and confirm they load **without needing to sign in** — Google's reviewer
   checks this, and both are fully static.

## Use these URLs in Play Console

- **Data safety → Delete account URL:** your `delete-account.html` URL from step 3
- **Store listing → Privacy Policy:** your `privacy.html` URL from step 3

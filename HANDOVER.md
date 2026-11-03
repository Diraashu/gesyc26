# GESYC / GESMUN Website — Handover Guide

This site is built to be passed down year to year. Everything is one file
(`index.html`) plus an `assets/` folder — no frameworks, no build steps,
nothing to install. Any future team member with a GitHub account can run it.

## How the site is organised

| What | Where |
|---|---|
| Event date / countdown target | `index.html` → search `CONFIG` |
| Committees (names, agendas, briefs, EB) | `index.html` → search `COMMITTEE DATA` |
| Core Secretariat (names, roles) | `index.html` → search `CORE SECRETARIAT` |
| Registration link | `index.html` → search `register-btn` |
| Download links (brochure, matrix, guides) | `index.html` → search `dl-btn` |
| Committee logos | `assets/logos/` (lowercase names, e.g. `terra.png`) |
| Secretariat photos | `assets/organizers/` (see README there) |
| Heading font | `assets/fonts/` + the `@font-face` rule |
| Source documents each year | `STUFF/` (never shown on the site) |

## Yearly handover checklist

1. **Move the repo to a shared home (do this once):** create a GitHub
   **Organization** (e.g. `gesmun-goodearth`) using a neutral email the school
   controls (e.g. a dedicated Gmail like `gesmun.goodearth@gmail.com`), and
   transfer this repository into it (repo Settings → Danger Zone → Transfer).
   The site URL becomes `https://<org-name>.github.io/<repo>/`.
2. **Each year:** the outgoing team adds the incoming web-head as an org
   member (org Settings → People). Nobody ever needs the old owner's password.
3. **Archive the year:** before editing for the new year, create a branch
   named after the old year (`git branch gesyc26-final`) so every year's
   site is preserved forever and can be re-published any time.
4. **Update content** per the table above; push; the live site updates itself.
5. **Domain:** `gesneoforum.com`, registered at GoDaddy (auto-renew ON).
   DNS: four A records (@ → 185.199.108–111.153) + CNAME www → the GitHub
   Pages host. The repo's `CNAME` file must always contain `gesneoforum.com`.
   Keep the GoDaddy login in the handover envelope with the shared Gmail
   credentials.

## Rules of thumb

- Photos/logos: keep filenames lowercase, no spaces.
- Test on a phone before big announcements (the drawer menu, the carousel).
- Never commit passwords or personal data — this repo is public.

## Performance notes (keep it fast on phones)

- **Images:** committee logos and the hero emblem are `.webp` (see `assets/logos/README.txt`).
  Organiser photos are 256x256 JPGs (`assets/organizers/<name>.jpg`), gallery photos are
  ~1600px-wide JPGs. Never upload raw camera files (5-10 MB) - resize them first.
- **Font:** the heading font is loaded as `Cronisse-Regular.woff2` (the `.ttf` is only a fallback).
- **Hosting limit:** GitHub Pages sets a short browser-cache lifetime that we can't change.
  Lighthouse will always flag "efficient cache lifetimes"; that is expected. The fix (if ever
  needed) is putting a free CDN such as Cloudflare in front of the domain.

## Event phase switch (before / after the event)

The home page has two versions built in, controlled by ONE attribute on the `<body>` tag in `index.html`:

- `data-phase="after"`  -> "Thank You" + "Stay tuned for the next edition" (what GESYC '26 uses now)
- `data-phase="before"` -> live countdown + "Registrations Open" + the register button

**To start a new edition:**
1. Change `<body data-phase="after">` to `data-phase="before"`.
2. Set `EVENT_START` in the script (search `CONFIG`) to the new start date/time.
3. Update the dates written in the hero, footer and the two meta/og descriptions at the top of the file
   (search for `October 2026`), and the "Rescheduled" tooltip text if the date moves again.
4. Replace the registration form link (search `forms.gle`).
5. Reword the WhatsApp panel blurb (search `wa-blurb`) and update committees / EBs / gallery as needed.

**When the event ends:** set it back to `data-phase="after"` and reword the "Held ..." dates.
Add the new year's photos at the top of the Gallery page.

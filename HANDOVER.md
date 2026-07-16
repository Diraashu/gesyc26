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
5. **Domain (if bought):** register it with the shared email, enable
   auto-renew, and keep the registrar login in the handover envelope along
   with the shared Gmail credentials.

## Rules of thumb

- Photos/logos: keep filenames lowercase, no spaces.
- Test on a phone before big announcements (the drawer menu, the carousel).
- Never commit passwords or personal data — this repo is public.

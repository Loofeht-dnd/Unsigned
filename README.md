# Unsigned — the werewolf party game

A single-file werewolf party game: classic pass-and-play (offline)
plus online mode — everyone on their own phone, join by room code.

## Deploying on Render

1. Push this repo to GitHub (see below).
2. Render dashboard > **New** > **Blueprint** > select the repo.
3. Render reads `render.yaml` and deploys with no further settings.
4. You get a `https://unsigned-xxxx.onrender.com` URL — HTTPS included.

### One-time setup after deploying

Supabase dashboard > Authentication > URL Configuration:
add your production URL (e.g. `https://unsigned-xxxx.onrender.com`)
as an allowed Site URL / redirect URL.

## Game-night notes

- Supabase free tier pauses after ~a week idle; a dashboard visit
  wakes it up.
- Anonymous signups are rate-limited (~40/hour/IP) — fine for a
  party, may trip on repeated testing from one Wi-Fi.
- Offline pass-and-play works with no connection after the page
  loads once.

## Rebuilding

In the main workspace: `python rebuild.py`, then copy the new
`index.v2.html` over `index.html` here and push. Render redeploys
automatically.

Also deployed on Vercel; pushes to main redeploy automatically.

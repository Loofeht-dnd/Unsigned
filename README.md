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

## Unsigned 4.3 expansion pass

This update builds on the 4.2 pass with richer map cards and field notes for Barrio, Haunted Island, and Space Station; map-specific visual accents; expanded local achievements; and three additional house-rule presets (Last Stand, Open Book, Quiet Village). Presets are combinations of existing house rules; they do not add new role mechanics or change role resolution.

The archive and avatar preferences are stored locally in the browser on each device. They are not synced to Supabase. Existing maps, role cards, sound ambience, end-of-game statistics, and online/offline play are retained.


The 4.2 visual profiles (Cinematic, Modern, Illustrated), reduced-motion setting, per-player avatar color accents, local game archive, existing maps, role cards, sound ambience, end-of-game statistics, and online/offline play are retained. Local archive records now also track map selection, task progress, and special-role count to support the expanded achievements. These records remain on the current device and are not synced to Supabase.


## Unsigned 4.8 gameplay expansion

Offline pass-and-play now uses the expanded 15-game task minigame engine previously used by online play. The existing offline task completion, night-action limit, save/resume, and dawn resolution flow are retained. No backend schema changes or additional dependencies are required.

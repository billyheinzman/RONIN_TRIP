# Ronin's Mission 🚀

A phone-friendly checklist app for Ronin: a Tuesday/Wednesday chores list
and a San Diego trip packing list. Taps save automatically on his phone,
and a progress ring fills as he checks things off (with confetti at 100%).

It's a single static page — no build step, no backend.

## Sending progress updates
There's a green **Email Update** button at the bottom. When Ronin taps it,
his phone's email app opens with a message pre-filled to
**billyheinzman@gmail.com** showing what's done and what's left
(chores + packing). He just taps Send. To change the recipient, edit the
`EMAIL_TO` line near the top of the `<script>` in `index.html`.

## Files
- `index.html` — the whole app
- `manifest.json` — lets him "Add to Home Screen" as an app
- `icon-192.png` / `icon-512.png` — app icons
- `vercel.json` — clean URLs config

## Deploy to Vercel (via GitHub)
1. Create a new GitHub repo (e.g. `ronin-mission`) and upload these files
   to the root of the repo.
2. Go to vercel.com → **Add New → Project** → import that repo.
3. Framework Preset: **Other**. Leave build/output settings empty.
4. Click **Deploy**. You'll get a URL like `ronin-mission.vercel.app`.

## Put it on Ronin's phone
1. Open the Vercel URL in **Safari (iPhone)** or **Chrome (Android)**.
2. Tap the Share button → **Add to Home Screen**.
3. It opens full-screen like a real app, and his checkmarks are saved
   right on his phone.

## Editing the lists later
All the chores and packing items live in the `CHORES` and `PACKING`
objects near the top of the `<script>` in `index.html`. Edit the text,
commit to GitHub, and Vercel redeploys automatically.

> Note: progress is saved per-device in the browser. If he clears his
> browser data or switches phones, the checkmarks reset.

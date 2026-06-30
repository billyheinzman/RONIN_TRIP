# Ronin's Mission 🚀

A phone-friendly checklist app for Ronin: a Tuesday/Wednesday chores list
and a San Diego trip packing list. Taps save automatically on his phone,
a progress ring fills as he checks things off (confetti at 100%), and
**you get automatic emails** as he makes progress.

## Files
- `index.html` — the app
- `api/notify.js` — serverless function that sends the emails
- `manifest.json`, `icon-192.png`, `icon-512.png` — home-screen app setup
- `vercel.json` — config

## Automatic progress emails
You get an email at three moments (no action needed from Ronin):
- 🚀 when he checks off his first task
- 💪 when he hits 50%
- 🏆 when everything is done (with the full list)

There's also a **Send Update Now** button he can tap anytime to email you
the current status on demand.

All emails go to the address you set in `NOTIFY_TO` (see setup below).

## One-time setup (about 10 minutes)

### A) Deploy the app
1. Upload all files (keep the `api` folder) to a GitHub repo.
2. vercel.com → Add New → Project → import the repo → Framework: Other → Deploy.

### B) Get a free email key from Resend
1. Go to **resend.com** and sign up (free — 3,000 emails/month).
2. In the dashboard, open **API Keys → Create API Key**. Copy it
   (it starts with `re_`).

### C) Add the key to Vercel
1. In your Vercel project: **Settings → Environment Variables**.
2. Add two variables:
   - `RESEND_API_KEY` = the key you copied (the `re_...` value)
   - `NOTIFY_TO` = billyheinzman@gmail.com
3. Click **Save**, then go to **Deployments → … → Redeploy** so the keys
   take effect.

### D) Put it on Ronin's Samsung
1. Open the Vercel URL in Chrome → ⋮ menu → **Add to Home screen**.

## Test it
- Open the app, check off one task → you should get the "🚀 started" email.
- Or tap **Send Update Now** → the button shows "✅ Sent!" and you get an email.
- If the button shows "⚠️ Failed", the Resend key isn't set yet (do step C).

## Notes
- Emails arrive **from** `onboarding@resend.dev` (Resend's free sender).
  They may land in Spam the first time — mark "Not spam" once.
- Checkmarks save on Ronin's phone only; the emails are how you see status.
- To change which moments trigger emails, edit `checkMilestones()` in
  `index.html`.

# the clean swap — go live in ~1 hour (no terminal needed)

This folder is everything you need to put the app online for a week.
Two files do the work:
- `index.html` — the app (scanner + Sophie chat)
- `api/messages.js` — a tiny secure backend that holds your API key

You never paste your key into the webpage. It lives only in Vercel, hidden.

---

## STEP 1 — Get your Anthropic API key + set a safety budget (10 min)

1. Go to **console.anthropic.com** and sign in.
2. **Billing** → add a small amount of credit (e.g. $10–20).
3. **Billing → Limits** → set a **monthly spend limit** (e.g. $20).
   This is your seatbelt: even if a reel goes viral, billing stops at the cap.
4. **API Keys** → **Create Key** → copy it (starts with `sk-ant-...`).
   Keep it private. Anyone with this key can spend your credit.

## STEP 2 — Put these files on GitHub (15 min, all clicks)

1. Go to **github.com**, sign in (free), click **+ → New repository**.
2. Name it `clean-swap`, keep it Public or Private, click **Create**.
3. On the repo page click **uploading an existing file**.
4. Drag in **index.html**, **README.md**, AND the **api** folder
   (drag the whole `api` folder so `api/messages.js` stays inside it).
5. Click **Commit changes**.

## STEP 3 — Deploy on Vercel (15 min, all clicks)

1. Go to **vercel.com**, **Sign up with GitHub** (free).
2. **Add New… → Project** → **Import** your `clean-swap` repo.
3. BEFORE clicking Deploy, open **Environment Variables** and add:
   - **Name:**  `ANTHROPIC_API_KEY`
   - **Value:** paste your `sk-ant-...` key
4. Click **Deploy**. After ~1 minute you get a link like
   `https://clean-swap.vercel.app`.
5. Open it and test: scan a label, ask Sophie something. If it works, you're live.

## STEP 4 — Share it on Instagram (5 min)

1. Paste the Vercel link in your **bio** ("link in bio").
2. Post a **Story** with the **Link sticker** pointing to it, so people
   tapping through your reels land straight on it.
3. Mention it in a reel: "Comment / tap the link to try my swap checker."

## STEP 5 — After one week (2 min)

- Remove the link from your bio.
- In Vercel, open the project → **Settings → Pause** (or delete it).
- Costs come only from usage, so once nobody is calling it, spending stops.
  (Your STEP 1 spend limit guarantees it anyway.)

---

## Costs, honestly
Every label scan and every Sophie message runs on your API key — a few cents
each. With heavy traffic that adds up, which is exactly why STEP 1's spend
limit matters. Set it before you share the link, not after.

## Your logo
Your TCS logo is already built into the app (header, footer, results, and the
shareable Instagram cards). Nothing to do.


## If something breaks
- App loads but scanning/chat fails → the API key isn't set right.
  Vercel → Settings → Environment Variables → confirm `ANTHROPIC_API_KEY`,
  then **Redeploy**.
- "Missing ANTHROPIC_API_KEY" message → same fix as above.

# Laerskool Fairland Rugby Scoreboard
### GitHub Pages + Ably — free, permanent, no server needed

---

## How it works

```
Your phone (index.html)
    │  publishes score updates via Ably
    ▼
Ably (free relay — cloud)
    │  pushes to all subscribers instantly
    ▼
Anyone's browser (glru-scoreboard.html)
```

Live scores appear on the public scoreboard within ~1 second of tapping + or −.
Works for anyone with the link — phone, laptop, big screen TV.

---

## One-time setup (~10 minutes)

### Step 1 — Get a free Ably API key

1. Go to **https://ably.com** and click **Sign up free** (no card needed)
2. Create an app — name it anything e.g. "LF Rugby"
3. On the app dashboard, click **API Keys**
4. Copy the default key — it looks like: `AbCdEf.GhIjKl:MnOpQrStUvWxYz`

### Step 2 — Paste the API key into both HTML files

Open **`index.html`** and find this line near the top of the `<script>`:

    const ABLY_API_KEY = 'YOUR_ABLY_API_KEY_HERE';

Replace `YOUR_ABLY_API_KEY_HERE` with your actual key.

Open **`glru-scoreboard.html`** and do the same — search for `YOUR_ABLY_API_KEY_HERE`.

Use the SAME key in both files.

### Step 3 — Enable Message History on the Ably channel

This lets the scoreboard instantly show current scores when someone opens the link mid-match.

1. In your Ably dashboard → your app → **Channel Rules**
2. Click **Add new rule**
3. Channel namespace: `glru-scoreboard`
4. Enable **Persist last message**
5. Save

### Step 4 — Put files on GitHub Pages

Files are hosted at: **https://github.com/Lolifier4527/LaerskoolFairland**

1. Upload these 3 files:
   - `index.html`
   - `glru-scoreboard.html`
   - `1780310267995_Skool_Logo.png`
2. Go to **Settings → Pages**
3. Source: **Deploy from a branch** → `main` → `/ (root)` → Save

After ~1 minute your site is live at:

    https://lolifier4527.github.io/LaerskoolFairland/

---

## Match day

1. Open your GitHub Pages URL on your phone
2. Tap **📺 SCOREBOARD** — a popup shows the shareable scoreboard link
3. Share that link — WhatsApp it to parents, put it on a big screen, anything
4. Score as normal — every tap updates everyone's screen in ~1 second

The scoreboard shows a **● LIVE** indicator when connected.

---

## Email results

- On **mobile**: tapping "Send Email" opens your phone's mail app
- On **PC/desktop**: tapping "Send Email" opens your default desktop mail client via mailto:
- Results go to **sport@laerskoolfairland.co.za**

---

## Age Groups

9A · 9B · 9C · 10A · 10B · 10C · 11A · 11B · 11C · 4DE · 3DE · 2DE · 1STE

---

## Free tier limits

| What | Free allowance |
|------|---------------|
| Messages/month | 6,000,000 |
| A full match day (both fields) | ~500–1,000 messages |

---

## Troubleshooting

- **"WAITING FOR APP"** — API key not pasted in, or haven't tapped 📺 SCOREBOARD yet
- **"✕ OFFLINE"** — Check API key in glru-scoreboard.html; check internet
- **Scores don't update** — API key must be identical in both files
- **New viewer sees 0–0 mid-match** — Set up Message History in Ably (Step 3)

# FlowDeck — Daily Planner & Productivity Score

A Notion + TickTick + Calendar inspired productivity dashboard. Plan tomorrow tonight, track completion during the day, score your night, and get AI coaching.

## Quick Deploy to Vercel (5 minutes)

### Step 1 — Unzip the project
```bash
unzip flowdeck.zip -d flowdeck
cd flowdeck
```

### Step 2 — Push to GitHub
1. Go to https://github.com/new
2. Create a new repo named `flowdeck` (Private is fine)
3. In your terminal, inside the `flowdeck` folder:
```bash
git init
git add .
git commit -m "Initial FlowDeck deployment"
git branch -M main
git remote add origin https://github.com/YOUR_USERNAME/flowdeck.git
git push -u origin main
```
(Replace `YOUR_USERNAME` with your actual GitHub username.)

### Step 3 — Deploy on Vercel
1. Go to https://vercel.com/new
2. Sign in with GitHub
3. Click **"Import Project"** → select `flowdeck`
4. Vercel auto-detects Next.js. Leave defaults:
   - Framework Preset: Next.js
   - Build Command: `next build`
   - Output Directory: `.next`
5. Click **Deploy**
6. Wait ~2 minutes — Vercel gives you a live URL like `flowdeck-abc123.vercel.app`

### Step 4 — Open and use
Visit your Vercel URL → click **"Load Example Routine"** → start planning!

---

## Run Locally (optional)

```bash
bun install     # or: npm install
bun run dev     # or: npm run dev
# Open http://localhost:3000
```

---

## Features

- **Dashboard** — Today's score, streaks, XP/level, weekly progress, motivational quote
- **Tasks** — Full CRUD with priority, category, tags, repeat rules, time estimates
- **Calendar** — Monthly view with score-colored cells
- **Reports** — 30-day trends, weekly bars, category pie, 12-week heatmap
- **Achievements** — XP, levels, 12 badges, rank ladder
- **Nightly Review** — Per-task Yes/No/Partial + reflection + AI Coach
- **AI Coaching** — Uses z-ai-web-dev-sdk to analyze your day and give specific feedback
- **PWA** — Installable on iPhone/Android home screen
- **Offline-first** — All data stored in browser localStorage

## Score Formula (customizable in Settings)

`Score = Completed×60% + Priority×20% + Habits×10% + TimeAccuracy×10%`

- 95-100 = Excellent
- 85-94 = Great
- 70-84 = Good
- 50-69 = Needs Work
- Below 50 = Poor

## Tech Stack

- Next.js 16 (App Router) + TypeScript
- Tailwind CSS 4 + shadcn/ui (New York)
- Recharts for charts
- Zustand for state (localStorage persisted)
- next-themes for dark/light mode
- z-ai-web-dev-sdk for AI coaching

## Troubleshooting

**Build fails on Vercel?**
- Make sure `bun.lock` and `package.json` are both pushed to GitHub
- Vercel will auto-install dependencies

**AI Coach button returns error?**
- The endpoint at `/api/ai-analysis` uses `z-ai-web-dev-sdk`
- Should work out of the box on Vercel — no env vars needed in this sandbox setup

**Notifications not working on iPhone?**
- iOS requires you to install as PWA first (Safari → Share → Add to Home Screen)

**Data lost after redeploy?**
- Data lives in browser localStorage, not on the server
- Use Settings → Data → Export JSON to backup before redeploying

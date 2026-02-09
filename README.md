# EV Lock — Auto-Hedge Engine for Polymarket

Auto-hedge your prediction market positions using the **Max If Win (Free Roll)** strategy. Zero downside, maximum upside.

## Deploy to Vercel

### Option A: GitHub → Vercel (Recommended)

1. Create a new GitHub repo and push this project
2. Go to [vercel.com/new](https://vercel.com/new)
3. Import your GitHub repo
4. Click **Deploy** — Vercel auto-detects Create React App
5. Done — you'll get a live URL like `ev-lock.vercel.app`

### Option B: Vercel CLI

```bash
npm i -g vercel
cd evlock-vercel
vercel
```

Follow the prompts. Done in 60 seconds.

## How It Works

**Max If Win** hedges the minimum amount on the opposite side to break even if your bet loses:

- **If your bet wins →** full profit minus small hedge cost
- **If your bet loses →** $0 (break-even)

This converts any in-profit position into a **free roll** — you can't lose.

### The Math

```
Hedge Stake = Cost Basis / (Opposite Odds - 1)
```

Where `Opposite Odds = 1 / (1 - Current Price)`.

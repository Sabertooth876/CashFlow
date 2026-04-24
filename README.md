# Cashflow v2 — Personal Finance PWA

Multi-currency personal finance tracker. Data stored locally on your device. No accounts, no servers.

## What's new in v2

- **Multi-currency (JMD + USD)** — enter transactions in native currency; totals auto-convert
- **Live exchange rate** — Refresh button pulls latest USD→JMD rate (or edit manually)
- **Budgets per category** — monthly limits with visual progress bars (green → yellow → red)
- **End-of-month forecast** — projected income, expense, net based on current pace
- **Income breakdown** — Salary vs Freelance shown separately
- **Monthly reports** — drill into any past month with full stats
- **Custom categories** — add your own beyond the built-in list
- **Search & filter** — find transactions by text, type, or category

## Deploy (5 minutes)

### Option A: Netlify Drop (fastest, no signup)

1. Unzip the folder on your computer
2. Go to https://app.netlify.com/drop
3. Drag the `cashflow` folder onto the page
4. Get your URL (e.g. `https://quick-name-123.netlify.app`)
5. Open URL in Safari on iPhone → Share → Add to Home Screen

### Option B: GitHub Pages (permanent, prettier URL)

1. Create account at github.com
2. New repository (public), name it `cashflow`
3. Upload all 5 files, commit
4. Settings → Pages → Source: `main` branch, `/ (root)`
5. Wait 1 min, URL appears: `https://YOUR-USERNAME.github.io/cashflow/`
6. Open in Safari → Share → Add to Home Screen

## First-time setup (Jamaica config)

1. Open the app
2. Tap the gear icon (top right)
3. Confirm Primary: JMD, Secondary: USD
4. Tap Refresh next to the exchange rate — pulls live USD/JMD rate
5. Go to Auto tab (bottom) → + New and set up each recurring:

| Entry | Type | Currency | Frequency | Category |
|---|---|---|---|---|
| Monthly salary | Income | JMD | Monthly | (Salary) |
| Rent | Expense | JMD | Monthly | Rent |
| Internet (Flow/Digicel) | Expense | JMD | Monthly | Internet |
| Electricity (JPS) | Expense | JMD | Monthly | Electricity |
| Water (NWC) | Expense | JMD | Monthly | Water |
| Postpaid data | Expense | JMD | Monthly | Postpaid Data |
| Spotify | Expense | USD | Monthly | Spotify |
| Crunchyroll | Expense | USD | Monthly | Crunchyroll |
| PSN | Expense | USD | Monthly | PSN |
| Claude | Expense | USD | Monthly | Claude |

6. Go to Insights tab → + Budget and set monthly limits on anything you want to control (Food, Entertainment, Gas, etc.)
7. Each new manual entry → tap the + button, enter amount, pick category, done

## How currency conversion works

- Each transaction stores its native currency (truth preservation — your US$11.99 Spotify charge stays US$11.99)
- Dashboards and totals convert to your primary currency (JMD) using the current exchange rate
- If you change the rate later, past USD entries re-convert automatically
- USD amounts display with `US$` prefix, JMD with `J$` prefix
- Below each USD entry, a converted hint: `US$11.99 ≈ J$1,858.45`
- The Refresh button uses exchangerate-api.com (free, no API key, no signup)

## Backup discipline — critical

Your data lives in browser localStorage on your phone only. If you clear Safari data or uninstall the PWA, data is gone.

- Settings → Export JSON every 1-2 weeks
- Save the file to iCloud Drive or email it to yourself
- If your phone dies, install the PWA on your new phone and Import JSON to restore everything

## Features not built yet (if you want them later)

- Push notifications (iOS PWA limitation — Apple restricts this)
- Face ID / PIN lock on the app
- Receipt photo attachments
- Tags (separate from categories, e.g. "reimbursable")
- Cloud sync (would need a backend service)
- Multi-device real-time sync

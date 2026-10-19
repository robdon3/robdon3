# Aingen

A Next.js personal finance and life dashboard. It is a browser app for comparing the time cost and full cost of decisions, not a connection to a bank.

Sample figures ship with the UI (a fictional "John Doe" household, round balances, employer "Tech Corp"). They are not a real ledger. Choosing a blank start skips that sample. No account numbers are stored in the repo.

## What it is

After a local sign-in, a tabbed screen covers a main dashboard, fuel costs, true cost of a purchase, financial health, net worth, time value of a purchase, life-stage context, location-based tax inputs, insight cards, account entry, a FRED key setting, a Census panel, tax helpers, and a privacy panel. The Census panel states that no API key is required. State figures come from a table in `components/CensusAPIService.ts`, not from a live Census call.

## Problem

Everyday money choices hide maintenance, tax, and opportunity cost. Aingen is a single place to enter those inputs and see them together, with data kept in the browser unless cloud sync is configured.

## Approach

```text
Browser (Next.js / React)
  login form
  localForage (accounts, preferences, API keys)
  calculators and trackers
        │
        ├─ optional  /api/redis/*     Upstash Redis
        ├─ optional  /api/fred/*      FRED series (key from the request)
        └─ Census figures             bundled table, no API key
```

Passwords are hashed in the browser with SHA-256 (`js-sha256`) and stored with the local user record. That is not a server-side identity provider. "AI insights" are local cards and sample spending patterns in the client, not a trained model.

Economic screens fall back to built-in rates when no FRED key is set. Redis is optional; the app is written to keep working on local storage when Redis is absent.

## Run

Node.js 18+.

```bash
npm install
cp env.example .env.local   # optional keys; placeholders only
npm run dev
# http://localhost:3000
```

`FRED_API_KEY` turns on live Federal Reserve series. `UPSTASH_REDIS_REST_URL` and `UPSTASH_REDIS_REST_TOKEN` turn on the cloud-storage routes. Leave them blank to stay local.

```bash
npm run lint
npm run build
```

Playwright tests live in `tests/e2e.spec.ts` (`@playwright/test` is a dev dependency). They register users at `@example.com` and do not use real financial data.

## Tech

Next.js 14, React 18, TypeScript, Tailwind CSS, Recharts, localForage, Zustand, Upstash Redis client, Papa Parse, Lucide, Playwright.

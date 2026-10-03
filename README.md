# PairPilot — Agentic Dating Demo

## What it is
A working, consent-first prototype of an agentic dating site:
1. Add a person with LinkedIn + public Instagram URLs and consented profile facts.
2. The agent extracts explicit interests/tags.
3. Open a profile analysis.
4. Run agent-to-agent dates.
5. Generate a ranked list for every person.

## Important sourcing constraint
This prototype intentionally does **not** implement LinkedIn scraping. LinkedIn's current rules prohibit third-party crawlers/bots/scrapers and restrict use/display of scraped content. Use an official/authorized API where available, or collect profile facts directly from consenting participants.

## Run
Open `index.html` directly in a browser, or:
```bash
python -m http.server 3000
```
Then visit http://localhost:3000

## Deploy
This is a static site. It can be deployed to Vercel Drop or any static host. Vercel documents that Drop can deploy a folder directly and that Next.js deployments are supported.

## Demo
Click **Load 25-person demo**. The 25 demo identities are fictional/consented placeholders and are deliberately not presented as real people.

## Production architecture
- Frontend: React/Next.js + TypeScript
- Auth/consent: Clerk/Auth.js or equivalent
- Storage: Postgres/Supabase
- Agent orchestration: server-side LLM calls
- Official data ingestion: only APIs/exports or user-supplied facts with consent
- Matching: structured preference vectors + explainable pairwise scoring
- Audit: source provenance + consent timestamp + deletion controls

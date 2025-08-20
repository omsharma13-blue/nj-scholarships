# NJ Scholarships

A simple Next.js + Tailwind site to help New Jersey students find scholarships.

## One‑Click Deploy (after you push this repo to your GitHub)

[![Deploy with Vercel](https://vercel.com/button)](https://vercel.com/new/clone?repository-url=https://github.com/omsharma13-blue/nj-scholarships)

> Replace `YOUR-USERNAME` after you upload this code to your GitHub account.

## Local Development

```bash
npm install
npm run dev
```

Visit http://localhost:3000

## Pages
- `/` – Home
- `/scholarships` – Scholarship directory (sample data in `data/scholarships.json`)
- `/resources` – NJ programs (HESAA, EOF, NJ STARS)

## Tech
- Next.js 14
- Tailwind CSS 3

## Next Steps
- Swap JSON data for a Google Sheet or Airtable (API) so non‑technical contributors can add scholarships.
- Add search/filter by county, GPA, deadline.
- Add user accounts to save scholarships (Supabase/Firebase).


---

## Connect to Google Sheets (No-Code)

1. Create a Google Sheet with columns: **Name | Deadline | Amount | Eligibility | Link**.
2. In Google Sheets: **File → Share → Publish to web** (entire sheet).  
3. Copy the CSV link (or use this format replacing `SHEET_ID` and sheet name):  
   `https://docs.google.com/spreadsheets/d/SHEET_ID/gviz/tq?tqx=out:csv&sheet=Sheet1`
4. In local dev, create `.env` from `.env.example` and paste your link:
   ```bash
   cp .env.example .env
   # open .env and set SHEET_CSV_URL=...
   ```
5. On Vercel: **Project → Settings → Environment Variables**, add:
   - `SHEET_CSV_URL` = (your CSV link)
6. Redeploy. The `/scholarships` page will pull from your sheet automatically (falls back to `data/scholarships.json` if not set).


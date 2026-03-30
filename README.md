# Job Hunt Starter Kit
### 5-job trial — completely free setup

---

## Files in this repo

| File | What it is |
|---|---|
| `profile.json` | Your info — fill this ONCE, use it everywhere |
| `applied_jobs.csv` | Your application tracker — add one row per application |
| `prompts/1_rank_jobs.txt` | Paste into Claude to rank your 5 scraped jobs |
| `prompts/2_tailor_resume.txt` | Paste into Claude to get keyword-tailored bullets |
| `prompts/3_cover_letter.txt` | Paste into Claude to get a cover letter |
| `prompts/4_screening_questions.txt` | Paste into Claude to answer Workday questions |
| `prompts/5_follow_up.txt` | Paste into Claude to write follow-up emails |

---

## Step-by-step for your 5-job trial

### One-time setup (do this first)
1. Edit `profile.json` with your real info
2. Install Simplify extension: https://simplify.jobs → Add to Chrome → fill your profile there too
3. Create a free Apify account: https://apify.com

### Every morning (for 5 jobs)

**Step 1 — Scrape 5 jobs on Apify (2 min)**
- Go to apify.com → Store → search "linkedin jobs scraper"
- Set input: your job title + location, datePosted: past24Hours, maxResults: 5
- Run it → Export CSV when done

**Step 2 — Rank the 5 jobs with Claude (3 min)**
- Open claude.ai
- Copy `prompts/1_rank_jobs.txt`
- Paste your profile.json + the Apify CSV rows into it
- Claude gives you a ranked list — pick your top 3-5

**Step 3 — For each job you want to apply to:**

a) **Tailor resume (90 sec)**
   - Copy `prompts/2_tailor_resume.txt`
   - Paste the job description + your current bullet points
   - Claude shows you only the lines that changed
   - Open your Word resume → swap those lines → Save As PDF → name it `YourName_Resume_CompanyName.pdf`

b) **Get cover letter (30 sec)**
   - Copy `prompts/3_cover_letter.txt`
   - Paste the same job description + your profile
   - Copy the output — ready to paste

c) **Apply on the portal**
   - Open the apply link
   - Simplify auto-fills 80% of Workday/Greenhouse/Lever forms
   - For any free-text questions → use `prompts/4_screening_questions.txt`
   - Upload your PDF resume
   - Paste the cover letter
   - Review everything → Submit

d) **Log it (30 sec)**
   - Open `applied_jobs.csv` → add one row
   - Set follow_up_date = today + 10 days

**Step 4 — Follow up (10 days later)**
   - Check applied_jobs.csv for today's follow_up dates
   - Use `prompts/5_follow_up.txt` → send the email

---

## Costs for the 5-job trial
- GitHub: FREE
- Simplify: FREE
- Apify: FREE ($5 credit/month, 5 job scrapes uses maybe $0.02)
- Claude.ai: FREE tier

## When you're ready to scale to 50 jobs/day
- Apify: still free or $49/mo for heavy use
- Claude Pro: $20/mo (needed if you hit message limits)
- Schedule Apify to run automatically at 7am daily
- Consider n8n (free self-hosted) to automate the Apify → Claude → email digest pipeline

---

## Tracker column reference

| Column | Example |
|---|---|
| date_applied | 2025-03-30 |
| company | Stripe |
| role | Senior Backend Engineer |
| portal | Workday / Greenhouse / Lever / LinkedIn Easy Apply |
| jd_url | https://stripe.com/jobs/xxx |
| status | Applied / Interviewing / Rejected / Offer / Withdrawn |
| resume_version | v1_stripe (what you named the PDF) |
| follow_up_date | 2025-04-09 |
| keyword_score | 10/12 |
| notes | Distributed systems, Go mentioned twice in JD |

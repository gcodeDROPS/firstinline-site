# FirstInLine (working name) — One-Pager

## What I built
An AI-powered job-hunt command center that finds B2B sales jobs **before they get flooded** and writes the outreach that **gets replies**.

## The problem
Job seekers all use the same boards, see the same postings, and apply late — competing with 500+ applicants per role. Recruiters get 200 identical "I'm a motivated self-starter" messages and ignore almost all of them.

## How I built it (the story)
I was hunting for my own SDR/BDR role and got tired of the standard grind. So I built a system the way a good sales rep builds pipeline:

1. **A scraper engine** (Python + Oxylabs API) that runs targeted "search dorks" against direct ATS boards (Greenhouse, Ashby), LinkedIn hiring posts, and VC-backed startup job boards — catching postings early, before they flood.
2. **An AI enrichment layer** (Google Gemini) that reads each lead against my resume, scores the match, extracts the clean company name, and writes a personalized outreach note under 150 characters.
3. **A dashboard** that turns it all into a command center: match scores, source badges, one-click hiring-manager LinkedIn searches, and ready-to-send messages.
4. **A dedup cache** so I never burn API credits on the same posting twice.

Each run produces ~40 fresh, deduplicated, AI-scored leads with a direct application link and a tailored outreach message for every single one.

## What it does (for a user)
- **Finds early-signal leads:** direct ATS postings, stealth startups, VC portfolio boards, and managers posting "we're hiring" directly on LinkedIn — before the applicant flood.
- **Scores every lead:** AI match score against *your* resume, so you spend time on the right roles.
- **Writes your outreach:** a 150-character LinkedIn note and a cold email, personalized per company.
- **Tracks your pipeline:** applied → replied → interview → offer, like a sales CRM for your job search.
- **Sends a weekly digest:** "7 new early-signal leads this week" straight to your inbox.

## Who it helps (everyday people)
- **SDRs, BDRs, AEs** (the core audience): salespeople who know the game and want an edge.
- **Any competitive job seeker:** recent grads, career switchers, people in crowded fields (marketing, product, design, engineering) — anyone applying to roles where being early and personal wins.
- **People who hate networking theater:** the tool writes the personalized note for you; you just send it.

## The unfair advantage
Most job tools (Teal, Jobright, Huntr) show you the same flooded postings everyone else sees. This finds the ones **before** they flood — the way a great sales rep finds pipeline before the market does. And it speaks the language of the person using it: pipeline, ICP, outreach, follow-through.

## The pitch in one line
**"Treat your job search like a sales pipeline — find the role before the flood, and get a reply when you reach out."**

## Status
Working MVP (my own job hunt is the live demo). ~40 leads per run, ~893 Oxylabs credits in the tank, dashboard live. Next: validation, productize, launch.
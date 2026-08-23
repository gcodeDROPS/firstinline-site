# Business Plan — FirstInLine (working name)
**AI Job-Hunt Command Center for Sales Professionals**
Founder: Joseph Goydish II | Date: 2026-08-22 | Status: Pre-launch (MVP built)

---

## 1. Executive Summary

FirstInLine is a subscription web app that treats a job search like a sales pipeline. It finds B2B sales job postings **before they flood** (direct ATS boards, stealth startups, VC portfolio boards, LinkedIn hiring posts), scores each lead against the user's resume using AI, and generates personalized outreach messages that get replies.

**The wedge:** generic job-search tools (Teal, Jobright, Huntr) show the same 500-applicant postings to everyone. FirstInLine finds early-signal opportunities and does the personalization work that actually moves the needle — for the one audience that understands pipeline thinking: salespeople.

**Model:** freemium SaaS. Free tier (throttled, weekly runs) → Pro $29/mo (daily runs, unlimited leads, all outreach features). Launch price $19/mo.

**Ask:** none external — bootstrapped, launchable for < $50 (existing VPS, existing Oxylabs credits, domain + Stripe only).

---

## 2. Problem

1. **Discovery is broken:** job seekers use the same boards and see the same postings, often applying days after posting — competing with 300-500+ applicants.
2. **Outreach is ignored:** recruiters receive hundreds of generic "motivated self-starter" messages. Personalization is the difference between a reply and a delete, but most people don't do it because it's tedious.
3. **No pipeline thinking:** job seekers don't track their search like a sales funnel — no follow-up cadence, no pipeline stages, no measurement. Salespeople know this is exactly how you win.
4. **Stealth/early roles are invisible:** the best opportunities (founding SDR at a YC startup, a manager posting "we're hiring" on LinkedIn) are the hardest to find — they sit on direct ATS pages and VC boards, not Indeed.

## 3. Solution

A web app that runs the user's job search like a sales motion:

- **Early-signal discovery engine** — targeted scraper (Oxylabs) across 4+ channels: direct Greenhouse/Ashby ATS postings, LinkedIn hiring posts, VC/YC portfolio boards, regional tech ecosystems.
- **AI scoring** — Gemini reads each lead against the user's resume and outputs a match score (90-99), clean company name, and "why you fit."
- **AI outreach generator** — a 150-character LinkedIn connection note + a short cold email, personalized per company, with placeholders.
- **Application CRM** — pipeline board: Saved → Applied → Replied → Interview → Offer.
- **Weekly digest** — email summary of new early-signal leads.
- **User profiles** — paste resume, pick target queries (role type, industry, location, remote).

## 4. Market

### TAM/SAM/SOM (conservative)
- **TAM:** ~4M US sales professionals (Bureau of Labor Statistics: sales & related occupations). Job seekers at any given time: ~10-15% → ~500K.
- **SAM:** tech/SaaS salespeople actively job hunting (SDR/BDR/AE): ~150-250K US.
- **SOM (year 1):** 500-1,000 paying users via organic + community distribution.

### Competition
| Tool | What it does | Gap FirstInLine exploits |
|---|---|---|
| Teal | Resume builder + job tracker | Generic boards, no early-signal, no outreach |
| Jobright | AI job matching | Late discovery, generic outreach |
| Huntr | Job application tracker | No discovery engine, no AI outreach |
| Sonara | Auto-apply | Spray-and-pray, no personalization |
| Simplify | Auto-fill applications | Speed, not signal |
| PathWise | Career coaching | Not a tool |

**Positioning:** "The salesperson's job search tool." We don't compete on volume — we compete on signal + personalization. The ICP *is* the marketing: salespeople understand "pipeline," "ICP," "outreach" instantly.

## 5. Business Model

### Pricing
| Tier | Price | Includes |
|---|---|---|
| Free | $0 | 5 leads/run, weekly runs, basic tracker |
| Pro | $29/mo ($19 launch) | Daily runs, unlimited leads, AI outreach, digest, priority support |
| Annual | $228/yr (2 months free) | Everything in Pro |

### Unit economics (targets)
- **Data cost per Pro user/month:** ~$1-2 (Oxylabs credits + Gemini). Daily runs × ~4 credits/run × ~$0.003-0.01/credit + Gemini pennies.
- **Gross margin:** > 90% at scale.
- **CAC:** $0-15 (organic/community-led; referral program).
- **LTV (12-mo avg retention):** ~$228-348. LTV:CAC > 15:1.
- **Churn reality:** job seekers churn when hired — that's the *success* outcome. Mitigate with referral gifts + alumni network.

### Revenue scenarios (Year 1)
| Scenario | Paying users | MRR | ARR |
|---|---|---|---|
| Conservative | 300 | $5,700 | $68K |
| Base | 600 | $11,400 | $137K |
| Stretch | 1,200 | $22,800 | $274K |

## 6. Go-to-Market

### Phase 0 — Validation (Week 1)
- Landing page + waitlist (one-pager pitch)
- 10 conversations with real salespeople → gate: 5 "I'd pay $19-29/mo"

### Phase 1 — Launch (Weeks 2-6)
- Build MVP (productize existing scripts → web app)
- Invite waitlist, dogfood (founder's own job hunt = live case study)
- **Content engine:** founder posts the journey on LinkedIn — he IS the ICP. "I built an AI tool to find my next SDR role" is the story.

### Phase 2 — Distribution (Week 8+)
- Communities: r/sales, r/SDR, r/techsales, SDR Discords, tech sales Slack groups
- Referral program: free month per referral; hired users gift months to their network
- Product Hunt launch + sales-coach/community partnerships
- **SEO:** "SDR job search," "how to find B2B sales jobs," "best job search tools for sales" content

### Phase 3 — Expand (Month 3+)
- Verticals: AE, CS, marketing, design, engineering
- Sources: Lever, Workable, SmartRecruiters, YC/VC APIs
- Features: interview prep, salary intel, company research packs, auto-apply drafts

## 7. Operations & Tech

### Stack (boring on purpose)
- **Backend:** Python (existing scripts) → FastAPI service
- **Data:** SQLite (start) → Postgres (scale)
- **AI:** Google Gemini API (existing key)
- **Scraping:** Oxylabs Realtime API (existing account, ~893 credits)
- **Frontend:** existing dashboard HTML → React/Next (only after validation)
- **Auth:** magic-link (email OTP) — no password storage
- **Payments:** Stripe Checkout (no subscription engine at first)
- **Email:** Resend (free tier)
- **Deploy:** this VPS, Docker, Caddy/nginx + Cloudflare
- **Cost to launch:** < $50

### Data & ToS compliance (critical)
- Scrape via Oxylabs (licensed data provider) — never resell raw scraped datasets
- Position product as "discovery + assistant," not a data broker
- Respect robots.txt, rate limits, per-source terms
- Privacy: user resumes are sensitive — encrypt at rest, never train on user data without consent, delete-on-request

## 8. Roadmap

| Phase | Timeline | Deliverables |
|---|---|---|
| 0. Validate | Week 1 | Name, domain, landing, 10 interviews, 5 yeses |
| 1. Productize | Weeks 2-3 | Secrets→.env, core package, multi-user, auth |
| 2. MVP | Weeks 4-6 | Feed UI, outreach generator, tracker, digest, deploy |
| 3. Monetize | Weeks 6-7 | Stripe, free/pro tiers, usage caps |
| 4. Launch | Week 8 | Waitlist → paid, Product Hunt, community push |
| 5. Scale | Month 3+ | Verticals, sources, AI upgrades, frontend rebuild |

## 9. Risks & Mitigations

| Risk | Severity | Mitigation |
|---|---|---|
| Scraping ToS (LinkedIn/ATS) | High | Oxylabs licensed provider; no raw resale; assistant positioning |
| Oxylabs credit cost | Medium | Dedup cache (built), usage caps, per-user throttling |
| Churn on hire | Medium | Referral gifts, alumni network, "success = churn" framing |
| Crowded market | Medium | Early-signal wedge + sales-native positioning; don't compete on volume |
| Founder distraction (job hunt) | Medium | Dogfood: the job hunt IS the demo; product ships while he searches |
| Single point of failure (one dev) | Low | Boring stack, documented scripts, freelance frontend later |

## 10. Team

**Joseph Goydish II — Founder.** 3.5+ years B2B cybersecurity SaaS sales (Cyberbit, FortifyData); self-taught security researcher with 5 NVD-published Apple CVEs (CISA KEV, CVSS 10.0); D1 NCAA athlete (discipline, coachability, composure under pressure). Built the entire MVP solo. He is the ICP, the first customer, and the marketing story.

## 11. Financial Plan (Year 1, base case)

### Costs
| Item | Monthly | Notes |
|---|---|---|
| VPS | $0 | existing |
| Oxylabs | $20-40 | scales with users; monitor |
| Gemini | $5-15 | pennies per run |
| Domain + email | $2 | |
| Stripe fees | 2.9% + 30¢ | variable |
| Total fixed | ~$30-60/mo | |

### Revenue (base case)
- 600 paying users × $19 avg = $11,400 MRR by month 12
- Ramp: 0 → 50 → 150 → 300 → 450 → 600 (organic + community)
- **Year 1 ARR: ~$137K, gross margin > 85%**

## 12. The Founder's Edge (why this wins or dies)

**Wins if:** the early-signal wedge is real (it is — the harvest proves it), the ICP responds to the sales-native pitch (they will — it's how they think), and the founder ships fast while living the problem (he is).

**Dies if:** validation shows salespeople won't pay (Phase 0 gate catches this before cost), or Oxylabs/ToS kills the discovery engine (mitigated by provider + positioning).

**Bottom line:** a $50 launch, a founder who is the customer, and a wedge no incumbent owns. Worst case: a great portfolio piece and a better job hunt. Best case: a real company.
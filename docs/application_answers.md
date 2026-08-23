# YC Work at a Startup — Application Answers (Joseph Goydish II)

Two versions: **General** (any startup/domain) and **Security** (cyber/appsec companies like RASPIRE).

---

## Q1: Describe yourself in a short phrase

### General (recommended)
> B2B SaaS sales rep with D1 athlete discipline who built an AI-powered pipeline to land his next role.

### General alternates
- "Sales operator who treats outbound like a season — relentless, coachable, numbers-driven"
- "3.5-year SaaS SDR with the work ethic of a college athlete and the curiosity of a self-taught engineer"
- "Revenue builder who applies research-grade rigor to every pipeline he touches"

### Security version (for cyber companies)
> Security researcher with 5 published Apple CVEs who sells to the security leaders he researches.

---

## Q2: What are you looking for? What would you like to avoid?

### General (recommended)
> **Looking for:** An early-stage or founding GTM role where I can own top-of-funnel and help build the playbook from zero. I've spent 3.5 years in B2B SaaS sales (Cyberbit, FortifyData) and I want to apply that to a product I genuinely believe in and can explain cold. I'm looking to develop full-cycle selling — moving from SDR/BDR into closing — and I want to work on a small, remote-first team where my work directly moves revenue. I care about products with real traction and a clear ICP, and teams that value feedback and ownership over process theater.
>
> **Would like to avoid:** SDR pods where you're a number in a dial-count machine with no strategy. Products I can't explain simply or don't believe in. Heavy bureaucracy and micromanaged activity tracking without ownership of outcomes. I'd rather be somewhere my voice shapes the motion.

### Security version (for cyber companies)
> **Looking for:** A founding or early GTM role at a security company where I can own top-of-funnel and build the playbook from zero. I've spent 3.5 years in B2B cybersecurity sales (Cyberbit, FortifyData) and I want to apply that to a product I can genuinely demo and defend technically. I'm drawn to deep-tech products (application security, threat intel, AI security) where my research background gives me credibility with buyers. I want to develop full-cycle selling and work on a small, remote-first team where my work directly moves revenue.
>
> **Would like to avoid:** SDR pods where you're a number in a dial-count machine. Products I can't explain technically or don't believe in. Heavy process over actual outreach. Micromanaged activity tracking without ownership of outcomes. I've seen both sides of how security teams buy — I'd rather be somewhere my voice shapes the motion.

---

## Q3: Project you're proud of (start to finish)

### General version — the AI job-hunt pipeline (recommended for non-security roles)
> **Building an AI-powered job-hunt command center — from idea to 40 qualified leads per run.**
>
> **Motivation:** I was tired of the standard job search — scrolling the same boards, applying late, competing with hundreds of applicants. I wanted to find opportunities *before* they got flooded, the way a good sales rep finds pipeline before the market does.
>
> **What I did:** I built a full pipeline, solo. First, a crawler that hits Oxylabs' scraping API with targeted search dorks to pull direct ATS postings (Greenhouse, Ashby), LinkedIn hiring posts, and VC-backed startup boards. Then an AI enrichment layer that scores each lead against my resume, extracts the company, and writes a tailored outreach note. Finally, a dashboard that turns it all into an actionable command center — match scores, hiring-manager LinkedIn searches, and ready-to-send messages for every lead.
>
> **The challenge:** Making it *actionable*, not just a list. I had to solve dedup across sources, manage API credit budgets so I wasn't burning money on duplicates, and force the AI output into a format I could act on — clean company names, real application URLs, notes under 150 characters. The hardest part was the last mile: turning raw scraped data into something that actually gets replies.
>
> **How I measured success:** Each run produces ~40 fresh, deduplicated, AI-scored leads — with a direct application link and a personalized outreach message for each one. I went from applying late to being first in line on early-signal postings, with a repeatable system I can run in minutes.
>
> **Why it matters for sales:** It's literally the sales motion — prospecting, qualification, personalization, follow-through — applied to my own pipeline. It shows I build systems, manage resources, and execute, not just talk about activity.

### Security version — the zero-click iOS attack chain (for cyber companies)
> **Reverse-engineering a zero-click iOS attack chain — from compromised device to 5 published CVEs.**
>
> **Motivation:** A device I was analyzing showed signs of compromise while in airplane mode — network traffic was still leaking through a shadow tunnel (utun2). Most people would have wiped it. I wanted to know *how* it got in, so I started pulling kernel telemetry and memory artifacts instead.
>
> **What I did:** I traced the infection back through the stack: a malicious AMR audio file triggering heap memory corruption in CoreAudio, then a pointer-authentication bypass in the AppleBCMWLAN driver that turned it into a kernel read/write chain — fully zero-click. I then mapped a second chain: a single malicious PNG walking through ImageIO (out-of-bounds write), WebKit (heap corruption), and Core Media (use-after-free) to full kernel compromise. I extracted IOCs, wrote YARA signatures, and documented the whole chain with Shannon-Hartley verification of the covert channel.
>
> **The challenge:** No access to Apple internals, no jailbreak, no vendor support — just device telemetry, logs, and patience. The hardest part was proving the chain end-to-end from artifacts alone, then coordinating responsible disclosure: reporting privately to Apple and US-CERT, escalating through Google, and getting fixes shipped in iOS 18.4.1.
>
> **How I measured success:** Five CVEs confirmed in the NVD (CVE-2025-31200, CVE-2025-31201, CVE-2025-43300, CVE-2025-24201, CVE-2025-24085), listed in CISA's Known Exploited Vulnerabilities catalog, and re-scored to CVSS 10.0 via CISA Vulnrichment. The research is published openly on my GitHub.
>
> **Why it matters for sales:** This is exactly the work my buyers are trying to defend against. When I'm on a call with a security leader, I don't read from a script — I've lived the threat they're worried about.
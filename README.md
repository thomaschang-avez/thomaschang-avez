# Thomas Chang

AI Automation Engineer at [Avenue Z](https://avenuez.com) — I build the agent and automation layer for a full-service digital marketing agency. Everything listed here ships to production and runs on real clients.

---

## Agents & Automation Pipelines

**[PR Newsjacking Pipeline](https://github.com/Avenue-Z/pr-newsjacking)** `private`  
4 sequential CrewAI agents running across 26 PR clients. Monitors 77 Muck Rack Slack channels, scores articles against client pitchbooks (1–10), matches Tier 1 reporters, drafts personalized 4-paragraph pitch emails, creates Google Docs, posts daily Slack summaries. All inference routes through Glean Chat API — client data never leaves the enterprise environment. Runs M–F 7am automatically.  
`Python` `CrewAI` `Glean Chat API` `Slack API` `Google Drive API` `Google Sheets`

**[Media Brief Builder](https://github.com/Avenue-Z/media-brief)** `private`  
Flask webhook that accepts a Google Form submission, returns `202` immediately, and runs a CrewAI pipeline in the background. Gathers reporter and outlet data from Glean enterprise search, builds a correctly-formatted brief (5 types: Interview, Intro, In-Person, Broadcast, Podcast — reverse-engineered from real Avenue Z briefs), delivers via Slack DM to the submitter. Deployed on Railway, auto-deploys on merge to main.  
`Python` `Flask` `CrewAI` `Glean API` `Slack API` `Railway`

**[Automation Intake Agent](https://github.com/Avenue-Z/automation-intake-agent)** `private`  
Glean conversational agent that parses natural-language automation requests from employees and creates structured Asana tasks with correct custom fields. Gemini-powered NLP.  
`Python` `Gemini / VertexAI` `Asana API` `Glean`

**[Auto Slide Decks](https://github.com/Avenue-Z/auto-slide-decks)** `private`  
Automated slide deck generation for the Performance Media team.  
`Python`

---

## Growth Tools & Lead Gen

**[SXSW Lead Gen App](https://github.com/Avenue-Z/avenue-z-lead-generator-sxsw)** → [aeo.avenuez.com](https://aeo.avenuez.com)  
Used live at SXSW 2026. QR code → 10-section AI Search Readiness Assessment → instant scored results page → email delivery via Resend → Google Sheets logging. Full funnel in a single Next.js app.  
`Next.js` `TypeScript` `Resend` `GA4`

**[Avenue Z Signal](https://github.com/Avenue-Z/avenue-z-signal)** `private`  
AI-powered website audit and conversion intelligence tool. Crawls any URL and scores it across GEO (AI search citability), Core Web Vitals, SEO, and conversion performance. Generates client-ready PDF reports. Zapier webhook integration.  
`Next.js` `TypeScript` `Groq / Llama 3.3 70B` `Firecrawl` `Google PageSpeed API` `jsPDF`

**[Shopify Migration Assessment](https://github.com/Avenue-Z/avz-shopify-migration-assessment)** · **[Short Version](https://github.com/Avenue-Z/avz-shopify-assessment-short)**  
Lead gen assessments scoring e-commerce brands on Shopify migration readiness. Two variants — full and conversion-optimized short form.  
`Next.js` `TypeScript`

---

## Data Pipelines & Glean Connectors

Five custom connectors syncing external tools into Avenue Z's Glean enterprise search (Z/OS):

| Pipeline | What it does | Trigger |
|----------|--------------|---------|
| **[Bing Webmaster → Glean](https://github.com/Avenue-Z/bing-glean-sync)** | Pulls SEO stats + top queries for all verified sites, indexes into Glean | Daily — GitHub Actions |
| **[Sitebulb ZOS](https://github.com/Avenue-Z/avenue-z-sitebulb-zos)** | Parses Sitebulb audit exports for 20 clients, diffs vs. previous run, Slack alert + Glean index | Monthly |
| **[Screaming Frog ZOS](https://github.com/Avenue-Z/avenue-z-screaming-frog-zos)** | Maps SF CSV exports to 48 X-Point Framework checks, diffs new/resolved issues, alerts and indexes | Manual / scheduled |
| **[Dash Social → Glean](https://github.com/Avenue-Z/dash-social-connection)** | Syncs Dash Social data into a Glean custom datasource | Scheduled |
| **[Peec AI Worker](https://github.com/Avenue-Z/glean-peec-worker)** | Cloudflare Worker — syncs Peec AI Projects, Prompts, Chats, and Brand Reports into Glean | Daily |

---

## Reporting & Dashboards

**[Avenue Z Reporting Platform](https://github.com/thomaschang-avez/avenue-z-reporting-thomas-version-)** `public`  
White-labeled multi-client marketing reporting platform built on the Supermetrics API. 13 report sections (GA4, Meta Ads, Google Ads, TikTok, LinkedIn, Shopify, HubSpot, Snapchat, Reddit, Bing, and more). Role-based auth — internal team view and scoped client portal. AI-generated narrative summaries via BigQuery + Gemini Flash. Live PR Placements via NewsAPI. Full Funnel Conversion Intelligence (FFCI) with PR-to-revenue correlation.  
`Next.js 15` `TypeScript` `Auth.js v5` `Supermetrics API` `BigQuery` `Gemini Flash` `Tremor` `shadcn/ui` `Vercel`

**[Paid Media Exec Report](https://github.com/Avenue-Z/paid-media-exec-report)**  
Daily executive snapshot of paid media performance across all clients and platforms. Supermetrics → Google Sheets → React dashboard.  
`JavaScript` `React` `Supermetrics`

---

## Internal Tools

**[Service Page Generator](https://github.com/thomaschang-avez/tamar-service-page-generator)** `public`  
Built for Avenue Z's Brand Lead. Fill out a form → AI generates complete WordPress-ready HTML matching Avenue Z brand guidelines and design system. Replaced several hours of manual design work per page.  
`Next.js 14` `TypeScript` `Tailwind CSS` `Groq / Llama 3.3 70B`

**[Email Signature Generator](https://github.com/Avenue-Z/avz-signature-generator)**  
Team-wide email signature generator with Avenue Z branding and legal disclaimer. Single-page HTML, no backend.

**[Z:OS Internal Chat](https://github.com/Avenue-Z/avenue-z-chat)**  
Internal AI chat interface for the Avenue Z team.  
`TypeScript`

---

## Open Source

**[geo-seo-claude](https://github.com/thomaschang-avez/geo-seo-claude)** `public`  
GEO-first SEO skill for Claude Code. Optimizes websites for AI-powered search engines — ChatGPT, Perplexity, Gemini, Google AI Overviews. 11 sub-skills, 5 parallel subagents, 6 JSON-LD schema templates. Full CRM pipeline: prospect tracking → automated proposals (€2.5K–€9.5K/mo tiers with ROI projections) → monthly delta reporting. PDF report generator with score gauges and visualizations. One-command installer. 14+ merged community PRs.  
`Python` `Claude Code Skills` `ReportLab` `Flask` `HTMX`

---

## Stack

**Languages** — Python · TypeScript · JavaScript · HTML  
**AI / Agents** — Gemini · Groq / Llama · Claude · VertexAI · CrewAI · Glean Chat API  
**APIs** — Glean · Slack · Google Drive · Google Sheets · Asana · Supermetrics · Firecrawl · Resend · NewsAPI · Serper  
**Web** — Next.js · Flask · Tailwind CSS · shadcn/ui · Tremor  
**Infra** — Vercel · Railway · Cloudflare Workers · GitHub Actions · Docker · BigQuery  

---

Avenue Z org: [github.com/Avenue-Z](https://github.com/Avenue-Z) — 25 repos, 107+ commits  
Email: thomas.chang@avenuez.com

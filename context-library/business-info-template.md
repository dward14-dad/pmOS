# Business Context: Douglas Ward — AI PM Portfolio

## The Framing

Douglas is operating as a one-person product studio. The "company" is him. The mission is dual-purpose:
1. Land a senior PM role at a SaaS company by demonstrating AI PM capabilities
2. Build real AI fluency — agents, LLMs, prototyping, shipping quality products — through actual projects

The job search IS the product. Interview Prep is the primary product being built and shipped. Every decision made on Interview Prep is also a demonstration of AI PM capability.

---

## Mission

Help job-seeking PMs practice and get hired faster using AI-powered interview coaching.

## Vision (6-12 months)

A purpose-built AI interview coach for PMs that's meaningfully better than generic tools like ChatGPT — because it knows PM interview patterns, stores and evolves your stories, and adapts coaching to how you actually answer.

---

## Primary Product: Interview Prep App

**Location:** `/Users/douglasward/Interview Prep` | Deployed on Vercel

**What it does:** AI behavioral interview coach. Users practice mock interviews with voice/text, get GPT-powered coaching feedback, and build a library of STAR stories over time.

**Target user:** Job-searching PMs (Douglas is user #1)

**Current state:**
- Deployed and functional
- GPT-4o-mini for coaching, GPT-4.1-nano for extraction
- Voice via browser Web Speech API (needs upgrade to OpenAI TTS + Whisper)
- No auth / no data isolation — critical fix before real users
- Flow requires story setup before practice — needs redesign
- Eval harness built and working

**Immediate roadmap:**
1. Clerk auth + userId data isolation
2. OpenAI TTS + Whisper voice upgrade
3. Flow redesign — practice first, stories emerge from answers
4. Answer history — save previous answers, surface as suggestions

---

## Secondary Product: Learning Eater App

**Location:** `/Users/douglasward/learning-eater-app` | Deployed, Neon + Clerk

**What it does:** Weekly meal planning app for families with picky eaters. Deterministic planning engine with minimal AI today.

**Target user:** Douglas's own family (picky eaters at home)

**Current state:** Further along technically. Clerk auth + Neon DB live. 33-phase build plan.

**AI opportunity:** Replace deterministic engine with LLM-generated plans that rules validate. Would make it genuinely AI-native and give Douglas hands-on experience with a different AI architecture pattern.

**Priority:** Secondary. Build when Interview Prep reaches a stable state.

---

## What "AI PM Capabilities" Means Here

The goal isn't just to use AI — it's to demonstrate the full stack of what an AI PM does:

| Capability | How Douglas is building it |
|---|---|
| Use agents for research | `/competitor-analysis`, `/user-research-synthesis` in PM OS |
| Use agents for feedback review | Multi-agent PRD review (`/prd-review-panel`), eval harness in Interview Prep |
| Roadmap with AI | Using PM OS skills to manage Interview Prep's roadmap |
| Build with LLMs | Interview Prep's coaching layer, eval harness, planned voice upgrade |
| Ship quality products | Both apps deployed; Interview Prep targeting real users |
| Prototype fast | Learning Eater AI meal gen, new Interview Prep features |

---

## OKRs — Q2 2026

**Objective 1: Land a senior PM role at a SaaS company**
- KR 1.1: Complete at least 5 first-round interviews
- KR 1.2: Reach final round at 2+ companies
- KR 1.3: Have a signed offer by end of Q2

**Objective 2: Ship Interview Prep to real users**
- KR 2.1: Add auth + data isolation (unblocks all real users)
- KR 2.2: Upgrade voice to OpenAI TTS + Whisper
- KR 2.3: Get 10 real users completing at least one practice session
- KR 2.4: Collect and synthesize first round of user feedback

**Objective 3: Demonstrate AI PM capability through real artifacts**
- KR 3.1: Ship one AI-native feature with a clear before/after (voice upgrade counts)
- KR 3.2: Build and run at least one agent-based workflow (competitor research, feedback synthesis)
- KR 3.3: Document one AI product decision with tradeoffs (decision log)

---

## North Star Metric

**Interview Prep:** Practice sessions completed by users who return for a second session within 7 days.

Why: A one-time user got curious. A user who comes back is getting value and building a habit. That's the behavior that leads to confidence and eventually to job offers.

---

## Competitive Landscape

**Direct competitors:**
- ChatGPT voice mode — general purpose, no PM-specific intelligence, no story memory
- Exponent — PM interview prep platform, structured content but not AI-adaptive coaching
- Pramp — peer-to-peer mock interviews, no AI coaching
- Yoodli — AI speech coach, not PM-specific

**Douglas's edge:** Purpose-built for PM interviews with STAR story integration, PM-specific rubrics, role-based question banks, and difficulty-adaptive follow-ups. ChatGPT is a hammer; this is a scalpel.

---

## Key Metrics to Track

**Product health (Interview Prep):**
- Sessions started vs. completed (completion rate)
- D7 return rate (users who practice again within a week)
- Average score improvement over sessions (are users getting better?)
- Voice usage rate (once upgraded)

**Job search:**
- Applications sent
- Response rate
- Interview conversion (screen → next round)
- Offers received

**AI PM capability:**
- Artifacts shipped (features, decision docs, analyses)
- Agent workflows built and run
- Learnings documented

---

## Tools

- **Development:** Next.js, TypeScript, Prisma, OpenAI API, Vercel
- **AI:** Claude Code (PM OS), ChatGPT (practice), OpenAI API (Interview Prep)
- **Job search:** LinkedIn, direct outreach
- **PM OS skills most relevant:** `/prd-draft`, `/competitor-analysis`, `/feature-metrics`, `/decision-doc`, `/prd-review-panel`, `/interview-prep`

---

**Last updated:** 2026-04-13

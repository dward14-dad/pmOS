# Active Projects Index

A reference for Douglas's current personal projects. Use this when context about his work is needed.

---

## Project 1: Learning Eater App

**Location:** `/Users/douglasward/learning-eater-app`
**Status:** Active, in-progress (33 implementation phases defined)
**Tech Stack:** Next.js (App Router), React, TypeScript, Tailwind CSS, shadcn/ui, Prisma + PostgreSQL, Zod, Vitest, Playwright

**What it is:**
A mobile-first weekly meal planning app for families with picky eaters. Parents pick 7 dinners; the app generates a full week of meals ensuring every child has reliable food options while still getting exposure to new foods.

**Core mechanic:**
Deterministic planning engine driven by child-food relationships (go_to / growing / practicing / not_yet). NOT an AI meal generator — the master plan explicitly calls this out.

**AI involvement:**
Minimal by design. AI is used only for food classification assistance (suggesting food categories and meal roles when adding new foods). AI never generates meal plans or overrides planner rules. Parents must confirm AI suggestions before saving.

**Key docs:**
- `docs/master_plan.md` — product overview and rules
- `docs/implementation_plan.md` — architecture and APIs
- `docs/tasks_v2.md` — 33-phase task list

**Deployment:** Live. Neon (PostgreSQL) for database, Clerk for auth. More mature infrastructure than Interview Prep.

**AI-native assessment:** Low. The AI usage is a utility feature, not the core product. This project demonstrates product thinking and technical execution, but not AI-native product design.

**Potential to increase AI:** High — Douglas wants to lean into AI for actual meal plan generation, not just food classification. Opportunity: LLM generates plans that rules validate, or AI learns from family ratings over time. This would make it genuinely AI-native and match his personal motivation (real picky eaters at home).

---

## Project 2: Interview Prep

**Location:** `/Users/douglasward/Interview Prep`
**Status:** Active, deployed to Vercel
**Tech Stack:** Next.js (App Router), React, TypeScript, Tailwind CSS, shadcn/ui, Prisma (SQLite local / Neon PostgreSQL prod), OpenAI API

**What it is:**
An AI behavioral interview coach. Users build STAR stories, practice mock interviews with voice/text, and receive GPT-powered coaching feedback. Directly serves Douglas's current job search.

**Core AI architecture:**
- `gpt-4o-mini` — coaching feedback, story evaluation, interview analysis, follow-up questions
- `gpt-4.1-nano` — cheap extraction tasks (JD cleanup, resume parsing)
- All prompt templates in `lib/prompts.ts`
- Difficulty levels control follow-up depth: easy=0, standard=1, hard=2

**Key flows:**
- Build STAR stories mapped to question categories per role
- Practice mock interviews with AI-generated questions
- Get turn-by-turn coaching feedback with scores
- Eval harness (`npm run evals`) simulates 3 personas × N questions × 3 difficulties with a meta-evaluator prompt to validate coaching quality

**Deployment:** Live on Vercel. SQLite locally, Neon PostgreSQL in production.

**AI-native assessment:** High. LLMs are the core product — without the AI, there's nothing. Has a proper eval framework which shows sophisticated thinking about AI output quality.

**Voice gap:** Currently using browser Web Speech API (window.speechSynthesis + SpeechRecognition) — notably lower quality than ChatGPT voice. Upgrade path: OpenAI TTS API (tts-1-hd) + Whisper for STT, or OpenAI Realtime API for true streaming voice.

**Story potential:** This is the foundation for Story 6 (AI Menu App placeholder was misnamed — this is the real AI project). Strong "learning new technology" story — built a real AI-native product from scratch while job searching, complete with eval harness.

---

## What These Projects Demonstrate

| Dimension | Learning Eater | Interview Prep |
|---|---|---|
| AI-native | Low | High |
| Technical complexity | High (deterministic engine, complex rules) | Medium (LLM orchestration, prompt design) |
| Personal relevance | Relatable consumer problem | Directly serves his job search |
| Story fit | Execution, product thinking | AI/LLM fluency, learning agility |
| Interview talking point | "I ship real products" | "I understand AI-native design" |

---

**Last updated:** 2026-04-13

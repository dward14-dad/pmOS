# Interview Prep — Product Strategy 2026

**Author:** Douglas Ward
**Date:** April 13, 2026
**Status:** Draft
**Audience:** Internal alignment / PM portfolio artifact

---

## Executive Summary

Interview Prep is an AI behavioral interview coach built specifically for product managers. Where generic tools like ChatGPT require you to prompt-engineer your own coach every session, Interview Prep knows PM interview patterns, adapts to how you actually answer, and helps your stories improve over time.

The 2026 strategy has two phases. In the first half (April–June), the goal is quality and accessibility: get coaching quality above 90% satisfaction with a real eval framework, and open the product to real users beyond Douglas. In the second half (July–December), the goal is experience and retention: upgrade the voice interface to match ChatGPT-quality, redesign the practice flow to feel natural, and build the habit loop that brings users back.

**TL;DR:**
- **Objective:** Help job-searching PMs get to interview-ready faster through deliberate, PM-specific AI coaching
- **Target:** 10 active users with a D7 return rate above 40% by end of Q3
- **Approach:** Quality first, then accessibility, then experience
- **Strategic bets:** Own the daily practice habit for job-searching PMs + serve as the primary AI PM portfolio vehicle
- **Portfolio signal:** Demonstrates full-stack AI PM capability — eval harness, voice integration, flow design, prompt engineering

---

## 1. Objective

### Mission

Help job-searching PMs get hired faster through deliberate, PM-specific AI-powered interview practice.

### North Star Metric

**Practice sessions completed by users who return within 7 days (D7 repeat sessions)**

- Current baseline: 1 user (Douglas), no D7 data yet
- Target by end of Q3 2026: 40%+ D7 return rate across 10+ users
- Why this metric: A one-time session means curiosity. Coming back means the user got value and is building a habit. That habit is what leads to confidence and eventually to job offers.

### April OKRs

| Key Result | Target | Status |
|---|---|---|
| Eval criteria defined and running | Covers question quality, coaching depth, follow-up relevance | Not started |
| Coaching quality score | 90%+ satisfaction vs. eval rubric | Not started |
| Auth + user-level data isolation | Real users can sign up with isolated data | Not started |

### Supporting Metrics

1. **Session completion rate:** % of started sessions that reach the feedback summary
2. **Coaching score (per session):** Average quality score from eval harness
3. **D7 return rate:** % of users who complete a second session within 7 days
4. **Voice adoption rate:** % of sessions using voice vs. text (once upgraded)

### Guardrails

Metrics we won't sacrifice:
- Coaching quality score does not drop below 85% when adding new features
- No user data is accessible across accounts (data isolation is non-negotiable before any sharing)

---

## 2. Users

### Primary Segment: The Job-Searching PM

**Who:** Mid-career product managers (3–10 years experience) actively interviewing for their next role. Comfortable with technology, time-pressured, motivated but often underprepared for the behavioral portion of PM interviews.

**Pain:** They know their stories but can't tell them well under pressure. Generic tools (ChatGPT, friends) give feedback that's either too generic or too soft. Real mock interviews are hard to schedule and inconsistent in quality.

**Size:** Tens of thousands of PMs are in active job searches at any given time in the US. Douglas is user #1 and the primary validation source through end of Q2.

**Expansion horizon:** PMs are the beachhead. Once the core coaching loop is proven, expanding to other tech roles (engineers, designers, data scientists) is a natural growth path — the STAR framework and behavioral interview patterns apply across roles. Timing: explore in Q4 2026 once PM retention is proven.

### Jobs to Be Done

> "When I'm preparing for a PM interview, I want realistic practice with honest, specific feedback, so I can stop second-guessing my answers and walk into interviews with confidence."

**Current alternatives and why they fail:**

| Alternative | What it is | Why it falls short |
|---|---|---|
| ChatGPT | General-purpose AI | No PM rubric, no story memory, requires re-prompting every session |
| Exponent | PM interview content platform | Static — teaches frameworks but doesn't adapt to how you actually answer |
| Pramp | Peer mock interviews | Hard to schedule, quality varies, no AI coaching |
| Yoodli | AI speech coach | Voice-focused but not PM-specific, no STAR or behavioral depth |

**What success looks like for the user:**
- Feedback that's honest and specific, not generic encouragement
- Questions that push back the way a real interviewer would
- Stories that get tighter and more confident over time
- Something they can use independently, on their schedule

### User Journey (Current State)

1. **Discover** → Hears about tool, visits app
2. **Setup** → Must build STAR stories before practicing (current friction: feels like homework)
3. **Practice** → Mock interview with AI follow-ups
4. **Feedback** → Coaching summary with scores
5. **Return?** → Currently no strong pull to come back

**Biggest friction points:**
- Story setup before practice is a high barrier — users want to practice, not write essays first
- Voice quality (browser Web Speech API) is noticeably worse than ChatGPT voice, breaks immersion
- No account system means no saved progress, blocking any real users

---

## 3. Superpowers

### Superpower 1: PM-Specific Intelligence (Counter-Positioning)

Interview Prep is built around PM interview patterns — STAR structure, behavioral rubrics, role-based question banks, difficulty-adaptive follow-ups. ChatGPT could approximate this but only with heavy prompting each session. Generic tools won't invest in PM-specific depth because it's too narrow a niche for them. That narrowness is our advantage.

**Why it's durable:** The specificity compounds. Every improvement to the rubric, question bank, and coaching logic makes the tool more PM-native and harder for a general tool to replicate without explicit investment.

### Superpower 2: Eval Harness (Process Power)

Most AI interview tools ship prompts and hope. Interview Prep has a systematic eval harness (`npm run evals`) that simulates personas across questions and difficulties with a meta-evaluator. This is how we know coaching quality is above 90% — not by feel, but by measurement.

**Why it's durable:** This is operational infrastructure most competitors skip. It means quality improvements are testable and regressions are catchable. It also makes a strong portfolio signal: this is how AI PMs think about shipping AI features.

### Superpower 3: Builder-Led Product (Cornered Resource)

Douglas built this. He is the target user. He has 7+ years of PM interview experience on both sides of the table. The rubrics, question banks, and coaching logic reflect real PM interview patterns, not generic advice. That judgment can't be easily replicated by a team that doesn't live in this problem.

---

## 4. Vision

### Vision Statement

In 12 months, Interview Prep is the tool job-searching PMs recommend to each other. It feels like having a PM mentor available whenever you want to practice — one who knows your stories, pushes back like a real interviewer, and remembers how you've improved. You don't prep for interviews anymore. You just practice regularly, and the confidence comes naturally.

### What Changes

| Today | End of 2026 |
|---|---|
| 1 user (Douglas), no auth | 10+ active users, full account isolation |
| Browser speech API, low-quality voice | OpenAI TTS + Whisper, ChatGPT-quality voice |
| Stories required before practice | Practice first, stories emerge from your answers |
| No return mechanism | Habit loop: users come back because they see themselves improving |
| Eval harness exists, no published criteria | 90%+ coaching quality, measurable and documented |

---

## 5. Strategic Pillars

### Pillar 1: Coaching Quality You Can Measure

**What:** Define and hit a 90%+ coaching quality standard, validated by the eval harness, before opening to real users.

**Why:** If the coaching isn't genuinely better than ChatGPT, there's no product. Quality is the foundation everything else builds on. And building a measurable quality standard is itself the portfolio signal — it's how AI PMs should ship AI features.

**Key initiatives:**
- Define eval criteria covering question quality, coaching depth, follow-up relevance, score calibration
- Run evals across 3 personas × multiple questions × 3 difficulty levels
- Tune prompts until 90%+ satisfaction, document what changed and why

**Success looks like:** Eval harness runs cleanly, scores above 90%, and the criteria are documented well enough to rerun after any prompt change.

### Pillar 2: Real-User Readiness

**What:** Add authentication and user-level data isolation so the product can be used by anyone without data leakage.

**Why:** Everything else is blocked without this. You can't share the product, get real feedback, or build a D7 return metric without real users who have their own accounts.

**Key initiatives:**
- Clerk auth integration
- userId-scoped data throughout (stories, sessions, feedback)
- Basic account management (sign up, sign in, sign out)

**Success looks like:** Douglas can send the URL to 3–5 PMs in his network and they can sign up, practice, and have their data stay private.

### Pillar 3: An Experience Worth Returning To

**What:** Upgrade the voice interface and redesign the practice flow so the product feels good enough to use regularly, not just once.

**Why:** The current voice quality and story-first flow create friction that prevents habit formation. You can't hit a 40% D7 return rate if the experience feels clunky. This pillar is about removing the reasons users don't come back.

**Key initiatives:**
- OpenAI TTS + Whisper (or Realtime API) for voice that matches ChatGPT quality
- Flow redesign: practice first → AI surfaces answer themes → stories formalize from patterns
- Answer history: save previous answers, surface as suggestions in future sessions

**Success looks like:** Users who try the voice mode prefer it to text. Users who practice twice don't have to re-setup — their context carries forward.

### Non-Goals for 2026

- ❌ **Monetization:** No pricing, paywalls, or revenue focus. The goal is users and quality, not revenue.
- ❌ **Expanding beyond PM interviews in 2026:** PMs are the beachhead. Other roles (engineering, design) are a Q4 2026 question at the earliest — only after PM retention is proven.
- ❌ **Peer-to-peer features:** No connecting users with each other. Complexity without near-term payoff.
- ❌ **Mobile app:** Web is sufficient. A native app is a distraction from the core product.
- ❌ **Content library (articles, videos):** Exponent does this. We win on adaptive coaching, not static content.

---

## 6. Impact

### User Impact

**Users affected:** Job-searching PMs (10 targeted by end of Q3 2026)

**Value delivered:**
- Faster path to interview confidence — practice on your schedule, not when you can find a mock partner
- Honest feedback — the AI doesn't soften the critique the way a friend would
- Story improvement over time — answers get tighter session over session
- Voice practice — simulate a real conversation, not just typing answers

### Business / Portfolio Impact

This product is the portfolio. The impact isn't revenue — it's demonstrated AI PM capability across multiple dimensions:

| Capability | How Interview Prep demonstrates it |
|---|---|
| AI product quality | 90%+ eval score with documented criteria |
| AI architecture | Prompt design, multi-model routing (4o-mini + 4.1-nano), eval harness |
| Voice / multimodal | OpenAI TTS + Whisper integration |
| User-centric design | Flow redesign driven by real friction (story-first barrier) |
| 0→1 execution | Shipped a real product with real users, not just a prototype |
| Data-informed decisions | North Star + supporting metrics, D7 return rate tracking |

### OKR Alignment

| OKR | How strategy supports it |
|---|---|
| Land a senior PM role | Every artifact shipped = interview talking point; product itself is the demo |
| Ship Interview Prep to real users | Pillars 1 and 2 directly address this |
| Demonstrate AI PM capability | Eval harness, voice integration, flow design are all AI PM work |

---

## 7. Roadmap

### Now: April 2026 — Quality and Access

**Objective:** Validate coaching quality and open to real users.

| Initiative | Pillar | Milestone |
|---|---|---|
| Define eval criteria | Quality | Rubric documented, covers 4+ dimensions |
| Run evals + tune prompts | Quality | 90%+ satisfaction score achieved |
| Clerk auth integration | Real-User Readiness | Sign up / sign in working in prod |
| userId data isolation | Real-User Readiness | All data scoped per user, no cross-account leakage |

### Next: May–June 2026 — Experience

**Objective:** Make the product good enough to use regularly.

| Initiative | Pillar | Notes |
|---|---|---|
| OpenAI TTS + Whisper voice upgrade | Experience | Replace browser Web Speech API |
| Practice-first flow redesign | Experience | Remove story setup as a prerequisite |
| Answer history | Experience | Save answers, surface in future sessions |

### Later: Q3–Q4 2026 — Habit and Growth

**Objective:** Build the habit loop and get to 10 active users with 40%+ D7 return.

- Distribution: Share with PM network, communities (Lenny's, Product School, LinkedIn)
- Story evolution: Stories formalize and improve from repeated practice patterns
- Progress tracking: Show users how their scores change over time
- Potential: PM-community integrations (Slack bots, job board hooks) — explore based on user feedback

### Trade-Offs Made

**Monetization this year:**
- Considered adding a paid tier to validate willingness to pay
- Chose not to: Too early. No real users yet. Quality and habit come first. Revenue is a Q1 2027 question at the earliest.

**Expanding beyond PMs in 2026:**
- Considered targeting all tech job seekers (engineers, designers) now
- Chose not to yet: PM-specificity is the moat. The habit play only works if the tool is deeply good for one segment before broadening. Expansion is on the roadmap for Q4 once PM retention is proven.

**Building in public:**
- Considered tweeting/posting about the build for distribution
- Deferred: Better to have a polished product before bringing in an audience. Post-voice-upgrade is the right time to start building in public.

---

## Appendix

### Key Files
- Business context: `context-library/business-info-template.md`
- PM background: `context-library/personal-context-pm-background.md`
- Projects index: `context-library/projects-index.md`
- App location: `/Users/douglasward/Interview Prep`

### Open Questions
- What is the right distribution channel to reach the first 10 PM users? (Network, communities, LinkedIn)
- Should voice be TTS+Whisper (two separate APIs) or Realtime API (streaming, more complex)?
- What does the eval rubric need to cover to hit 90%? (Question quality, coaching depth, follow-up relevance, score calibration, tone)

### Next Review
- End of April: OKRs check-in — eval criteria hit? Auth shipped?
- End of June: Voice + flow done? First real users?
- End of Q3: D7 return rate check — are users coming back?

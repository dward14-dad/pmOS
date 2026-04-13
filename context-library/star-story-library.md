# STAR Story Library

Reusable behavioral interview stories. Each follows Situation → Task → Actions → Results.

---

## Story 0 — 90-Second Intro (Tell Me About Yourself)

See `personal-context-pm-background.md` for the full draft.

**Tags:** Opener, Career narrative

---

## Story 1 — Falsified Resume Screening (0→1 Product)

**Best for:** 0→1 execution, rapid prototyping, working with data science

**Situation:** A data scientist had developed an early concept for identifying falsified resumes that could indicate job applications from DPRK-linked actors. The concept showed promise but hadn't been productized.

**Task:** Work with data science, engineering, and design to turn the concept into a usable product and validate whether it could solve real customer needs.

**Actions:**
- Met with the data scientist and several customers to understand how organizations were currently identifying suspicious applicants
- Identified that speed, accuracy, and transparency of results were critical requirements
- Partnered with engineering and UI/UX to rapidly prototype a product experience
- Designed a workflow that provided not just a risk score but also contextual details explaining how the conclusion was reached
- Led the effort to bring the product to beta in approximately 2-3 months
- Used feedback from early users to refine both the ML model and the UX

**Results:**
- Generated over $1M in revenue in its first year
- Established a strong pipeline of interested customers prior to departure
- Demonstrated the company's ability to quickly productize advanced analytical models

---

## Story 2 — Open Source Software Risk (Hard Product Decision / Pivot)

**Best for:** Failure/pivot, product judgment, saying no, mentoring

**Situation:** Security teams were increasingly worried about vulnerabilities introduced through open source software. The team explored a product that would identify when individuals with ties to China, Russia, or Iran were contributing to open source projects used by enterprises.

**Task:** Prototype quickly, validate the market opportunity through a beta, and determine whether the product should move forward.

**Actions:**
- Worked with engineering and design to build a rapid prototype and launch a beta within 2-3 months
- Defined success metrics for the beta and helped onboard prospective customers
- Transitioned day-to-day product ownership to an APM while mentoring her through the beta process
- Met with prospects and existing customers to understand adoption barriers and perceived value

**Results:**
- The beta revealed the original positioning was difficult for prospects to operationalize
- Through customer conversations, uncovered a different, highly relevant use case for existing customers
- Redirected the effort toward that new initiative before departure — reused the underlying capability rather than abandoning the work entirely

---

## Story 3 — People Search (Driving Product Impact)

**Best for:** Strategy, 0→1, product impact, API/platform thinking

**Situation:** Organizations in sensitive sectors needed to evaluate whether individuals had ties to governments in China, Russia, or Iran before partnerships. An internal tool existed for one government client but wasn't designed as a scalable commercial product.

**Task:** Evaluate whether the capability could become a scalable commercial product, define the experience, and bring it to market.

**Actions:**
- Met with the growth team and several existing clients to understand how they evaluated geopolitical risk in individuals
- Identified a clear opportunity to productize for broader enterprise use
- Worked with design and engineering to define a UX that let customers search individuals and quickly identify risk signals
- Conducted design reviews and feedback sessions with prospective customers to validate the interface
- Built and executed a roadmap that first delivered a UI-based product, then expanded to an API offering so clients could integrate into their own workflows

**Results:**
- Generated over $1M in revenue within the first year
- Continued adoption grew it to over $13M in revenue — one of the company's highest-revenue products
- Established a scalable foundation that expanded the company's geopolitical risk intelligence offerings

---

## Story 4 — Org Search (Technical / Data Product)

**Best for:** Technical products, data visualization, customer discovery, complex trade-offs

**Situation:** Clients needed to understand relationships between organizations in China and Russia and their potential ties to government entities. A prototype existed and was occasionally demoed, but the experience was limited and the product wasn't fully developed.

**Task:** Turn the prototype into a scalable product by defining the core UX, prioritizing the right data relationships, and aligning development with real customer needs.

**Actions:**
- Partnered closely with a subject matter expert to deeply understand the underlying data and geopolitical relationships
- Brainstormed multiple approaches for visualizing relationships between organizations
- Collaborated with UI/UX to prototype several concepts for exploration and discovery
- Conducted sessions with the growth team and 3-4 prospective clients to understand their investigative workflows
- Used these conversations to prioritize trade-offs between data collection, feature scope, and development risk
- Led the launch of a redesigned interface with advanced search, detailed exploration, and the company's first network graph visualization

**Results:**
- Product grew to approximately $3M in revenue during tenure
- Continued growth expanded the product to over $8M in revenue after launch
- Graph-based relationship exploration became a key differentiator in the platform

---

## Story 5 — Product Pod Re-Org (Leadership / Influence)

**Best for:** Leadership, org design, influence without authority

**Status:** INCOMPLETE — needs to be filled in. Known context from resume: defined ownership, staffing priorities, and OKRs during transition to dedicated product pods.

---

## Story 6 — AI Menu App (Learning New Technology)

**Best for:** Learning agility, AI/LLM hands-on, personal initiative

**Status:** INCOMPLETE — this is one of Douglas's current personal projects. Fill in once the project is further along.

---

## Story 7 — Aligning Stakeholders with Conflicting Priorities

**Best for:** Conflict resolution, prioritization, AI product strategy, stakeholder alignment

**Situation:** At Strider, the product helping clients identify individuals with ties to foreign governments relied heavily on subject matter experts who manually reviewed profiles and surfaced a small set of high-confidence individuals. As the product gained traction, growth and product teams wanted to significantly expand scope to surface more signals and support a larger pipeline. Engineering and SMEs were concerned that expanding scope too quickly would reduce quality and credibility.

**Task:** Align competing priorities and develop a strategy that allowed scaling while maintaining the trust and accuracy the experts and customers required.

**Actions:**
- Facilitated discussions with growth, engineering, SMEs, and the Chief Product Officer to clarify trade-offs between scale and accuracy
- Proposed an iterative approach: expand scope first, then systematically improve quality through model and data improvements
- Identified opportunities to leverage emerging AI capabilities to improve data enrichment and signal confidence
- Developed a staged roadmap balancing automation with expert validation so the team could increase coverage without sacrificing credibility

**Results:**
- Achieved alignment across product, engineering, and domain experts on a balanced strategy
- Identified that the existing approach cost roughly $1,200 to produce 30-50 profiles per company per year using primarily manual SME enrichment
- By leveraging emerging AI capabilities from internal teams, created a plan to scale output to over 300 profiles per company per year at the same cost while maintaining the same depth and quality
- Expanded scope while maintaining trusted intelligence standards and enabling significantly greater coverage

---

## Story 8 — Data-Driven Product Improvement (People Search Success Rate)

**Best for:** Data-driven decisions, product metrics, iterative improvement, analytics

**Situation:** After launching People Search, a key product health metric was the failed search rate. As adoption grew, the team discovered that about 40% of searches were failing (roughly 60% success rate). Given the product's goal of helping customers quickly identify individuals and geopolitical risk signals, improving search success was critical to user trust and value.

**Task:** Investigate root causes behind failed searches and identify product improvements that could meaningfully increase the success rate without adding friction to the UX.

**Actions:**
- Analyzed search data to understand which inputs produced the highest success rates
- Discovered that searches including LinkedIn profiles had the highest match success, while many users were only entering a name and organization
- Facilitated brainstorming sessions with engineering to identify ways to increase LinkedIn data presence in searches
- Implemented three product improvements:
  1. Elevated LinkedIn in the search UI and simplified validation requirements
  2. Added a behind-the-scenes Google search to automatically detect LinkedIn profiles and append them to the query
  3. Integrated a third-party data source via API to retrieve missing profile data during the search process

**Results:**
- Increased People Search success rate from ~60% to over 80%
- Significantly reduced failed searches, improving user confidence in the product
- Demonstrated how product analytics could directly inform feature improvements

---

## Story 9 — Customer Feedback → AI Compliance Feature (Universities)

**Best for:** AI/LLM product thinking, customer feedback loops, innovation, adoption metrics

**Situation:** As the customer base expanded, a growing cohort of university clients were using the intelligence platform to stay compliant with regulatory requirements. Through conversations with Client Success Managers, consistent qualitative feedback emerged: universities found the process required a lot of manual interpretation and cross-checking.

**Task:** Better understand the workflow universities were using and determine whether a feature could help them more efficiently evaluate individuals against the regulations they needed to follow.

**Actions:**
- Met directly with several university clients to understand how they were currently using the product for regulatory compliance
- Identified that users were manually comparing the intelligence surfaced about individuals against specific compliance rules
- Proposed using an LLM-based approach to automatically compare information about an individual with the relevant regulations a university was applying
- Built initial experiments personally to test whether an LLM could meaningfully interpret regulatory language and match it with profile data
- After seeing promising results, conducted a virtual feedback tour with 6-7 university clients to validate the concept and gather workflow input
- Worked with engineering and legal teams to design and launch a production-ready version

**Results:**
- Delivered a new feature that significantly simplified how universities evaluated compliance requirements
- Achieved ~80% adoption among monthly active university clients after launch
- Demonstrated how qualitative customer feedback combined with emerging AI capabilities could create a differentiated workflow for a key customer segment

---

## Story Map — Which Story for Which Question

| Interview Question Type | Best Story |
|---|---|
| Tell me about yourself | Story 0 (90-sec intro) |
| Tell me about a product you launched from 0→1 | Story 1 (FRS), Story 3 (People Search) |
| Tell me about a time you drove significant revenue/impact | Story 3 (People Search, $13M) |
| Tell me about a hard product decision or trade-off | Story 2 (OSS Pivot), Story 7 (Stakeholder Alignment) |
| Tell me about a time you used data to improve a product | Story 8 (Search Success Rate) |
| Tell me about working with a technical team | Story 4 (Org Search), Story 1 (FRS) |
| Tell me about a time you failed or had to pivot | Story 2 (OSS Pivot) |
| Tell me about a conflict you navigated | Story 7 (Stakeholder Alignment) |
| Tell me about using AI in a product | Story 9 (AI Compliance), Story 7 (AI Scaling) |
| Tell me about customer discovery leading to a feature | Story 9 (Universities), Story 8 (Search Success) |
| Tell me about mentoring or developing others | Story 2 (APM mentoring), Story 5 (Pod Re-Org — TBD) |
| Tell me about a technical product | Story 4 (Org Search), Story 8 (Search Success) |
| Tell me about a time you learned something new | Story 6 (AI Menu App — TBD) |

---

## Metrics Bank

- People Search: $1M first year → $13M by departure
- Org Search: $3M during tenure → $8M+ after launch
- Falsified Resume Screening: $1M first year
- Entity resolution accuracy: ~80-85% → 90-95% (rule-based → ML-driven)
- People Search success rate: ~60% → 80%+
- AI Compliance feature adoption: ~80% among monthly active university clients
- AI scaling plan: 30-50 profiles/company/year → 300+ at the same $1,200 cost (6-10x improvement)
- Vivint Shortcuts: engaged 10% of target customer base
- myQ integration: doubled garage door controller compatibility while maintaining service costs
- Owens Corning: data visibility increased 150%; enabled $85M growth strategy via demand model
- Deloitte: cost savings up to 80% via audit specialist process; revenue audit efficiency +37%
- Zebra Technologies: app uploads +60%; trained 80 employees and 36 partners

---

**Last updated:** 2026-04-13

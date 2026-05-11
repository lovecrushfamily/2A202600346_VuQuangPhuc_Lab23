# 01 — Fact Check

This file documents the sources used to build the Day 23 submission in this repo.

Fact-check run date: **May 11, 2026**  
Method: **local repo inspection + live web search verification**

## 1. What was checked

The submission used three kinds of information:

1. **Local repo facts** from `A20-App-116` and this lab repo  
2. **External case-study facts** used in the case matrix, comparison, and dashboard rationale  
3. **Proposed pilot metrics** in `03-product-roi-dashboard.md`

Important distinction:

- Items in category 1 and 2 can be fact-checked.
- Items in category 3 are **not historical facts**. They are **proposed pilot baselines/targets** for a dashboard design exercise.

## 2. Local repo evidence

These claims were verified by reading the local repos directly, not by web search.

| Claim used in submission | Verified from | Why it matters |
|---|---|---|
| The Day 23 repo is a markdown submission repo with templates and assignment materials | [README.md](README.md), [Day23-Lab-Assignment.md](Day23-Lab-Assignment.md), [01-worksheet.md](01-worksheet.md) | Confirms the task is a documentation submission, not an app implementation task |
| `A20-App-116` includes a chat page and dashboard tab | [`A20-App-116/src/frontend/src/pages/Analyze.tsx`](../A20-App-116/src/frontend/src/pages/Analyze.tsx) | Supports the workflow choice in `03-product-roi-dashboard.md` |
| `A20-App-116` has a chat UI with cited sources panel | [`A20-App-116/src/frontend/src/components/analyze/ChatbotPanel.tsx`](../A20-App-116/src/frontend/src/components/analyze/ChatbotPanel.tsx), [`A20-App-116/src/frontend/src/components/analyze/CitedSourcesPanel.tsx`](../A20-App-116/src/frontend/src/components/analyze/CitedSourcesPanel.tsx) | Supports the “chat with cited sources” workflow |
| `A20-App-116` has a dashboard UI and PDF export flow | [`A20-App-116/src/frontend/src/components/analyze/DashboardPanel.tsx`](../A20-App-116/src/frontend/src/components/analyze/DashboardPanel.tsx), [`A20-App-116/src/frontend/src/lib/exportReport.ts`](../A20-App-116/src/frontend/src/lib/exportReport.ts) | Supports the dashboard review and PDF export workflows |
| `A20-App-116` has admin/observability UI but the endpoint is not fully implemented in the frontend | [`A20-App-116/src/frontend/src/pages/Admin.tsx`](../A20-App-116/src/frontend/src/pages/Admin.tsx) | Explains why the dashboard write-up treats some metrics as pilot-stage rather than live production metrics |
| `A20-App-116` backend exposes `/health`, `/chat`, `/recommend`, `/cv/upload`, `/jobs` | [`A20-App-116/src/backend/app/main.py`](../A20-App-116/src/backend/app/main.py) | Confirms what backend capabilities are clearly present in the reference repo |

## 3. External sources used and checked with live search

## 3.1 Klarna

### Claim used

In `01-case-evidence-matrix.md`, `02-case-comparison.md`, and `03-product-roi-dashboard.md`, I used the claim that Klarna reported strong AI support metrics, and that later reporting raised quality/course-correction concerns.

### Verification

| Source | What it verifies | Confidence |
|---|---|---|
| OpenAI case study: <https://openai.com/index/klarna/> | Klarna reported 2.3 million conversations, about two-thirds of support chats, 700 FTE-equivalent, 25% repeat-inquiry drop, and resolution time under 2 minutes vs 11 minutes before | High for “what Klarna/OpenAI reported”; this is company/self-reported evidence |
| Reuters coverage surfaced via search result: <https://www.investing.com/news/stock-market-news/europes-ai-poster-child-klarna-taps-the-brakes-on-chatbots-4233976> | Reuters reported on **September 10, 2025** that Klarna’s CEO said the company may have gone too far on AI cost cutting and was refocusing on service/product quality | High for the Reuters-reported course correction |

### Bottom line

The submission’s Klarna framing is supported:

- the strong productivity/cost claims are real, but company-reported;
- the later “don’t stop at volume/speed” lesson is supported by Reuters reporting on Klarna’s own correction.

## 3.2 Morgan Stanley

### Claim used

In `01-case-evidence-matrix.md` and `02-case-comparison.md`, I used Morgan Stanley as a trust-forward case where adoption happened in a high-risk environment because evaluation and controls came first.

### Verification

| Source | What it verifies | Confidence |
|---|---|---|
| OpenAI customer story: <https://openai.com/index/morgan-stanley/> | Morgan Stanley describes an eval-driven rollout, expert grading/feedback, compliance controls, and over 98% advisor-team adoption | High for “what Morgan Stanley/OpenAI reported”; this is company/self-reported evidence |
| Morgan Stanley press release: <https://www.morganstanley.com/press-releases/ai-at-morgan-stanley-debrief-launch> | Morgan Stanley states 98% of Financial Advisor teams adopted the Assistant | High for the adoption figure from Morgan Stanley itself |

### Bottom line

The submission’s Morgan Stanley lesson is supported, with one caveat:

- it is strong evidence for **adoption + trust architecture**,
- but it is still **company-reported**, not an independent audit of end-customer outcomes.

## 3.3 IBM Watson / MD Anderson

### Claim used

In the dashboard rationale and course notes, I used IBM Watson / MD Anderson as a caution that a famous AI brand and large investment do not guarantee operational adoption.

### Verification

| Source | What it verifies | Confidence |
|---|---|---|
| JNCI / Oxford Academic article: <https://academic.oup.com/jnci/article/109/5/djx113/3847623> | MD Anderson partnered with IBM Watson, spent years and major budget, and let the contract expire before Watson was used on actual patients | High; independent academic/news-style reporting in a peer-reviewed journal context |

### Bottom line

This cautionary reference is well-supported and appropriate.

## 3.4 DWP / GDS methodology references

### Claim used

In the dashboard rationale, I referenced DWP/GDS as examples that evaluation design matters, and that stronger methodology gives more defensible ROI/adoption conclusions.

### Verification

| Source | What it verifies | Confidence |
|---|---|---|
| GOV.UK GDS report: <https://www.gov.uk/government/publications/microsoft-365-copilot-experiment-cross-government-findings-report> | GDS ran a large experiment with 20,000 government employees across 12 organisations; the report explicitly focuses on productivity, efficiency, and user satisfaction | High |
| GOV.UK DWP evaluation: <https://www.gov.uk/government/publications/an-evaluation-of-dwps-microsoft-copilot-365-trial/an-evaluation-of-dwps-microsoft-365-copilot-trial> | DWP published a formal evaluation on **January 29, 2026**, using treatment and comparison groups plus econometric analysis to estimate impact on task efficiency, job satisfaction, and work quality | High |

### Bottom line

The submission’s “methodology matters” lesson is strongly supported.

## 3.5 KPMG and JPMorgan

### Claim used

In `03-product-roi-dashboard.md`, I used KPMG/JPMorgan as cautionary examples against measuring AI adoption only through usage volume or leaderboard-style tracking.

### Verification

| Source | What it verifies | Confidence |
|---|---|---|
| Business Insider search result for KPMG: <https://www.businessinsider.com/kpmg-dashboard-consultants-ai-adoption-use-tracker-employees-2026-5> | Search snippet reports KPMG launched an AI usage dashboard, benchmarked employees, and employees said it was easy to game | Medium-high; verified through live search result/snippet, but the full article was not directly opened cleanly |
| AOL syndication/search result: <https://www.aol.com/articles/kpmg-now-dashboard-where-consultants-154532433.html> | Repeats that KPMG tracks AI use against target goals and peer groups | Medium-high; syndicated copy/search result support |
| AOL search result on office AI leaderboards: <https://www.aol.com/news/office-ai-leaderboards-tell-us-083501680.html> | Reports that JPMorgan dashboards categorize employees as non/light/heavy users and rank AI usage | Medium; this is secondary reporting that cites Business Insider |

### Bottom line

These examples are useful and directionally supported, but they are **weaker than the OpenAI/GOV.UK/JNCI sources** because the proof here comes from search snippets and secondary/syndicated coverage rather than a directly opened primary report.

## 4. What in the dashboard is not a factual claim

The following items in [03-product-roi-dashboard.md](03-product-roi-dashboard.md) are **design proposals**, not facts:

- Baseline values such as `34%`, `18%`, `55%`, etc.
- Target values such as `60%`, `40%`, `80%`, etc.
- Suggested roles like `AI Ops Lead`, `Career Ops Lead`, `Growth Lead`
- The decision recommendation `pivot before scale`

These are valid for the assignment because the lab asked for a **Product ROI Dashboard design**, not a real post-launch company audit. I explicitly marked these as pilot assumptions in the repo README.

## 5. Source quality summary

| Source type | Examples | How I treated it |
|---|---|---|
| Primary company source | OpenAI Klarna, OpenAI Morgan Stanley, Morgan Stanley press release | Good for confirming what the company publicly claimed; not treated as neutral proof of total business impact |
| Government / official evaluation | GOV.UK GDS, GOV.UK DWP | Strongest evidence for methodology and impact measurement design |
| Academic / journal source | JNCI / Oxford Academic on MD Anderson + Watson | Strong independent cautionary source |
| Major news / Reuters | Reuters on Klarna course correction | Strong independent support for the “quality/course correction” point |
| Search snippet / syndicated business coverage | KPMG and JPMorgan dashboard stories | Used carefully and labeled as weaker than official reports |

## 6. Final honesty check

After fact-checking, I believe the submission is **defensible** if presented this way:

- The `A20-App-116` product analysis is grounded in the local repo.
- The Morgan Stanley, Klarna, DWP/GDS, and MD Anderson examples are supported by real sources.
- The KPMG/JPMorgan examples are directionally supported but should be presented as **cautionary media-reported examples**, not as hard audited findings.
- The numeric baselines and targets in the ROI dashboard are **proposed pilot metrics**, not historical facts.

If needed, the safest classroom phrasing is:

> “External case-study claims were verified with live search and cited here. Proposed dashboard baselines/targets are design assumptions for a pilot, not reported production numbers.”

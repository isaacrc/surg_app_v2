# Project Summary: SEC Filing Q&A Data Collection

**Date:** April 2026

---

A customer requested 100 Q&A pairs from SEC financial filings (10-K and 10-Q reports). We collect 120 to provide a buffer — rejected or contested items can be dropped and replaced without reopening collection. This is an open, self-paced project. Qualified workers on the platform claim individual tasks at their own pace, with no minimums, no deadlines, and no required pairings.

Here's the big picture: first, we identify expert annotators who actually know their way around a 10-K. Once candidates pass qualification (see `1_annotator_qualification/`), they join the worker pool and can begin claiming tasks. Each task involves either writing a Q&A pair from a set of assigned financial documents, or reviewing a submitted Q&A pair. Twelve company sets are available, each represented by a pre-structured CSV in `3_annotator_data/`. Workers enter their own worker ID and complete as many tasks as they choose. Once sufficient Q&As are collected and reviewed, the final 100 are compiled and delivered to the customer (see `4_quality_control/`).

![Phase Summary](phase_summary.png)

---

## Structure

The client wants 100 delivered Q&A pairs split into three categories — Category A, B, and C — which for simplicity we can think of as easy, medium, and hard. Category A Q&As can be pulled straight from a single filing; Category B Q&As require more digging (e.g., inferring something not directly stated or requiring calculation); Category C Q&As require synthesizing information across multiple filings.

**How are tasks organized?** The project uses 12 company sets, each covering 3 companies. Each set is its own task sheet (CSV) containing 10 Q&A slots: 3 Category A, 3 Category B, and 4 Category C. Workers can claim annotation or review tasks from any available set.

**Which sectors are covered?**

| Sector | Sets |
|--------|------|
| Technology | 3 |
| Healthcare | 2 |
| Energy | 2 |
| Financials | 3 |
| Industrials | 2 |
| **Total** | **12** |

Technology and Financials are represented three times given their prevalence in SEC filings and the depth of available annotator expertise in these sectors.

**Which financial documents do workers use?** Each company set includes a 10-K or 10-Q for each of its 3 companies; filing type per company is pre-assigned in the task sheet.

**Why collect 120 when we need 100?** The 20-item buffer ensures contested or rejected Q&As can be dropped and replaced from the reserve without reopening the collection phase.

---

## Output Quantity

| Category | Description | Per set | Collected (12 sets) |
|----------|-------------|---------|---------------------|
| Category A | Easy, single-document | 3 | 36 |
| Category B | Medium, single-document | 3 | 36 |
| Category C | Hard, multi-document | 4 | 48 |
| **Total** | | **10** | **120 → deliver 100** |

---

## Worker Tasks

Each Q&A item has two independent parts. Workers can complete either or both, across as many company sets as they choose.

- **Part 1 — Annotate:** Write one Q&A pair from a company set's assigned filings. Full instructions in `2_data_collection/2.1_annotation_instructions.md`.
- **Part 2 — Review:** Evaluate one submitted Q&A pair. Full instructions in `2_data_collection/2.2_review_instructions.md`.

Review tasks become available once a corresponding annotation is submitted. Any qualified worker can claim any annotation or review task — there is no sector-based matching requirement.

---

## Quality Assurance

We don't just trust the annotators blindly! Here's how we ensure Q&As are accurate before delivering to the customer.

- Blind review: each submitted Q&A is reviewed by a different qualified worker
- Rating scale: 0 (reject), 1 (revise), 2 (accept)
- For Rating 1: reviewer implements correction in bold; project lead accepts for Category A/B; rebuttal process applies for Category C and Rating 0
- $5 bonus per Category C Q&A that passes review on first submission, to incentivize harder questions

Full details in `4_quality_control/`.

---

## Qualification

Not just anyone can do this — we need people who read 10-K/10-Qs for a living. Full details in `1_annotator_qualification/`.

- Targeted outreach to equity research analysts, finance PhDs, CFA charterholders, and former investment banking analysts through Surge's expert network
- Paid ~60-minute qualification task; reviewed by project lead against clear pass/fail criteria

---

## Budget

Workers self-report hours and are paid at $20/hour. Expected times per task are provided as guidance (see `2_data_collection/`). The expected estimate below uses those times as a baseline; the high estimate assumes workers take ~25% longer on average.

**Annotation (120 Q&As):**

| Category | Count | Expected time | Base pay (expected) |
|----------|-------|---------------|---------------------|
| Category A | 36 | ~10 min each | ~$120 |
| Category B | 36 | ~15 min each | ~$180 |
| Category C | 48 | ~20 min each | ~$320 |
| **Subtotal** | | | **~$620** |
| Category C bonuses ($5 × 48) | | | ~$240 |
| **Annotation total** | | | **~$860** |

**Review (120 Q&As):**

| Category | Count | Expected time | Pay (expected) |
|----------|-------|---------------|----------------|
| Category A | 36 | ~5 min each | ~$60 |
| Category B | 36 | ~10 min each | ~$120 |
| Category C | 48 | ~15 min each | ~$240 |
| **Review total** | | | **~$420** |

**Full budget range:**

| Phase | Expected | High (+25%) |
|-------|----------|-------------|
| Qualification | ~$400 | ~$400 |
| Annotation | ~$860 | ~$1,015 |
| Review | ~$420 | ~$525 |
| **Subtotal** | **~$1,680** | **~$1,940** |
| +15% buffer | ~$250 | ~$290 |
| **Total** | **~$1,930** | **~$2,230** |

Qualification cost is fixed regardless of worker pace. The high estimate is the recommended planning figure.

---

## Timeline

Phases 2 and 3 run concurrently — review tasks open as annotations are submitted, and QA runs on a rolling basis. There are no fixed deadlines; the project closes once 100 approved Q&As are in the bank.

| Phase | Description |
|-------|-------------|
| Phase 1 — Qualification | Surge conducts targeted outreach to finance experts. Candidates complete a paid ~60-minute qualification task. The project lead reviews all submissions and admits qualified workers to the pool. |
| Phase 2 — Annotation & Review | Tasks posted to the platform. Workers claim annotation and review tasks at their own pace. Review tasks become available as annotations are submitted. Both parts run concurrently. |
| Phase 3 — QA & Revisions | Ongoing as submissions come in. Contested or rejected items enter the rebuttal/arbitration process. Project closes once 100 approved Q&As are collected. |
| Phase 4 — Delivery | Final 100 Q&As compiled and returned to the customer. |

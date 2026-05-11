# Quality Assurance: SEC Filing Q&A Data Collection

**Date:** April 2026

---

## Overview

All 100 submissions are reviewed before delivery. Quality assurance uses a single-reviewer blind peer review model, with sector-matched annotators reviewing each other's work. Payment to annotators is contingent on passing review.

---

## Review Structure

### Step 1: Blind Peer Review — all 100 submissions, 1 reviewer per submission

Reviewer assignments are made a priori, before annotation begins. Each annotator reviews the work of their sector-paired counterpart (the annotator assigned the same sector but different companies):

| Cohort 1 | | Cohort 2 |
|----------|---|----------|
| Annotator 1 (Tech) | ↔ | Annotator 6 (Tech) |
| Annotator 2 (Healthcare) | ↔ | Annotator 7 (Healthcare) |
| Annotator 3 (Energy) | ↔ | Annotator 8 (Energy) |
| Annotator 4 (Financials) | ↔ | Annotator 9 (Financials) |
| Annotator 5 (Industrials) | ↔ | Annotator 10 (Industrials) |

Because sector-paired annotators worked from similar company types, they have relevant domain knowledge for both easy/medium and hard (cross-company) questions.

For each of the 10 submissions they receive, reviewers assign one of three ratings:

| Rating | Meaning |
|--------|---------|
| 2 — Accept | Factually accurate, self-contained, correct difficulty level, source cited, no PII |
| 1 — Revise | Minor fixable issue; reviewer implements correction directly in the record using bold text |
| 0 — Reject | Factually wrong, not self-contained, or missing source |

For any submission receiving a rating of 1, the reviewer must explain exactly why the submission is insufficient and implement their proposed correction directly in the record using **bold text**, so that the record — as edited — would be acceptable at a rating of 2. Written reasoning must accompany every edit.

### Step 2: Internal Review

Once all 10 submissions have been reviewed and returned, the project lead processes the ratings and edits as follows.

**Rating 2 — Accept:** There is agreement between the annotator's submission and the review standard. No further action is required; the annotator is paid and the item is marked complete.

**Rating 1, Category A/B — Apply correction:** Easy and Medium questions involve verifiable facts — page citations, arithmetic, source identification — where a clear right answer exists. The project lead reviews the reviewer's bold edits and, if satisfied, accepts them. The annotator is paid. No further review round is needed.

**Rating 1, Category C — Rebuttal process:** Hard questions involve cross-document synthesis, where two finance-literate reviewers may reasonably interpret filings differently. The proposed correction is sent to the original annotator, who may either accept it or provide a counter-argument supported by specific evidence from the cited filings — one round of response only. The project lead reviews both arguments and makes a final call.

**Rating 0 — Reject:** Rejections are expected to be rare, as annotators are experienced professionals. If a submission receives a 0, the same rebuttal process applies as Category C: the item is returned to the original annotator with the reviewer's full reasoning, and the annotator may amend their submission or rebut the critique.

### Step 3: Arbitration

If conflict persists after the first round — that is, the original annotator disagrees with the review and does not accept the proposed change, whether the rating was 0 or 1 — the project lead determines the next step. Because a small buffer of extra tasks was collected, a contested item may simply be dropped and replaced with a task from the reserve pool, avoiding the need for further adjudication.

If disagreement is widespread across multiple Q&A items, the project lead will initiate a second arbitration round. Both arguments are forwarded to a third reviewer already in the pool, selected from an uninvolved sector pair. That reviewer votes on whether the annotator's or the reviewer's reasoning is most valid, and their decision is adopted.

---

## Reviewer Instructions

Reviewers must check each Q&A against the following criteria:

- **Self-containedness:** does the Supporting Facts section meet the standard for its category?
  - *Easy:* source citation with page number present
  - *Medium:* all calculation inputs provided with page numbers
  - *Hard:* each company-level claim has a cited fact or quoted language with filing and page; absent disclosures documented with where the reviewer looked

- **Accuracy:**
  - *Easy:* open the cited page and verify the fact is stated in the filing as the answer claims
  - *Medium:* independently run the calculations using the Supporting Facts values; flag if the result doesn't match the answer, or if a metric is misidentified (e.g., gross profit used instead of operating income)
  - *Hard:* confirm all cited filings are real and from October 2023 or newer; evaluate whether the overall synthesis is logically supported by the evidence cited; flag if an absent disclosure is not documented, a conclusion overstates what the evidence supports, or a causal/comparative claim is not logically justified

- **Correct difficulty level:** does this match Category A / B / C as labeled?
- **PII:** flag and anonymize any personal names, contact information, or identifying details

For any rating of 1, the reviewer must: (1) explain exactly why the submission is insufficient, (2) implement a correction directly in the record using **bold text** for all changes, and (3) provide a written rationale. See [2.1 — Revising the Submission](../2_data_collection/2.1_worker_facing_instructions.md#revising-the-submission) for the full revision process.

---

## Consistency

The rubric above serves as the primary consistency mechanism. Reviewers are already finance-literate (they passed the same qualification screen as annotators) and will have just completed the annotation task themselves, giving them practical intuition for the quality bar.

---

## Performance Bonus

Any annotator whose all 10 Q&As receive a rating of 2 on first submission earns a $25 bonus. This incentivizes high-quality first submissions and reduces revision load.

---

## QA Budget

**Rate: $20/hour**

| Phase | What this covers | Workers | Hrs | Cost |
|-------|-----------------|---------|-----|------|
| Peer review | Each annotator reviews their sector-paired counterpart's 10 Q&As | 10 | 17.5 | $350 |
| Performance bonuses | $25 per annotator with all 10 Q&As rated 2 on first submission (est. ~50% qualify = 5 of 10) | — | — | ~$125 |
| **Subtotal** | | | **17.5** | **~$475** |

**Estimated time per reviewer:**

| Category | Calculation | Time |
|----------|-------------|------|
| Category A | 3 × 5 min | 15 min |
| Category B | 3 × 10 min | 30 min |
| Category C | 4 × 15 min | 60 min |
| **Total** | | **1.75 hrs → $35/reviewer** |

**Timeline:**
- QA review: 3–5 days
- Revisions & delivery: 2–3 days

---

## Full Project Budget Summary

| Phase | Cost |
|-------|------|
| Qualification | ~$400 |
| Data collection | ~$667 |
| Quality assurance | ~$475 |
| **Subtotal** | **~$1,542** |
| +15% buffer | $231 |
| **Suggested total** | **~$1,773** |

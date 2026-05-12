# Quality Assurance: SEC Filing Q&A Data Collection

**Date:** April 2026

---

## Overview

Every annotation row is reviewed before it enters the delivery pool. Review is open — any qualified worker may review any completed row across any annotation set. Review is per-row, not per-set: a worker picks any row where `question` and `answer` are filled in but `Rating (for reviewer)` is empty, and submits their review. Payment for the review is self-reported via the `time_spent` column at $20/hour base, with per-question bonuses for Category B and C work.

---

## Review Structure

### Step 1: Peer Review — per row, open to all qualified workers

A completed annotation row becomes available for review immediately. Reviewers open any task set CSV via the shared Google Drive folder, find any row where `question` and `answer` are filled in but `Rating (for reviewer)` is empty, and assign one of three ratings:

| Rating | Meaning |
|--------|---------|
| 2 — Accept | Accurate, self-contained, correct difficulty level, no PII |
| 1 — Revise | Minor fixable issue; reviewer implements correction directly in the record using bold text |
| 0 — Reject | Factually wrong, not self-contained, or missing source |

For any rating of 1, the reviewer must: (1) implement the correction directly in the CSV row using **bold text** for all changes, and (2) write a rationale in the `Explanation (for reviewer)` column explaining what was wrong and why the change was made. Full reviewer instructions are in `../2_data_collection/worker_facing/2.2_review_instructions.md`.

### Step 2: Internal Review

The project lead processes submitted ratings as follows.

**Rating 2 — Accept:** No further action required. The row is marked complete and the annotator is paid.

**Rating 1, Category A/B — Apply correction:** Easy and Medium questions involve verifiable facts — page citations, arithmetic, metric identification — where a clear right answer exists. The project lead reviews the reviewer's bold edits and, if satisfied, accepts them. The annotator is paid; no further review round is needed.

**Rating 1, Category C — Rebuttal process:** Hard questions involve cross-document synthesis, where two qualified reviewers may reasonably interpret filings differently. The proposed correction is returned to the original annotator, who may either accept it or provide a counter-argument supported by specific evidence from the cited filings — one round of response only. The project lead reviews both arguments and makes a final call.

**Rating 0 — Reject:** Rejections are expected to be rare, as annotators are experienced professionals. The same rebuttal process applies as Category C: the row is returned to the annotator with the reviewer's full reasoning, and the annotator may amend their submission or rebut the critique.

### Step 3: Arbitration

If conflict persists after the first rebuttal round — the annotator disagrees with the review and does not accept the proposed change — the project lead determines the next step. Because 20 extra rows were collected as a buffer, a contested item may simply be dropped and replaced from the reserve pool, avoiding further adjudication.

If disagreement is widespread across multiple rows, the project lead will initiate a second arbitration round. Both arguments are forwarded to a third qualified worker not involved in the original annotation or review of that row. That worker votes on whether the annotator's or the reviewer's reasoning is most valid, and their decision is adopted.

---

## Review Checklist (Project Lead Reference)

The full review checklist is in `worker_facing/2.2_review_instructions.md`. In brief, reviewers check:

- **Self-containedness** — Supporting Facts meets the standard for its category: page citation for Easy; all calculation inputs with page numbers for Medium; per-company cited facts or quoted language with filing and page for Hard, with absent disclosures documented
- **Accuracy** — facts confirmed against the cited filing; calculations verified using Supporting Facts values; synthesis logically supported by cited evidence
- **Difficulty level** — Q&A matches its Category A / B / C label
- **PII** — no personal names, contact info, or identifying details

---

## Consistency

The shared rubric in `../2_data_collection/worker_facing/2.2_review_instructions.md` serves as the primary consistency mechanism. All reviewers passed the same qualification screen as annotators and are familiar with SEC filing structure, providing a consistent baseline for judgment.

---

## QA Budget

Review pay: **$20/hour** base, self-reported via `time_spent`. Per-question bonuses for Category B and C reviews.

| Category | Count | Time per review | Base pay | Bonuses | Total |
|----------|-------|----------------|----------|---------|-------|
| Category A | 36 | ~15 min | ~$180 | — | ~$180 |
| Category B | 36 | ~20 min | ~$240 | $2.50 × 36 = $90 | ~$330 |
| Category C | 48 | ~25 min | ~$400 | $5.00 × 48 = $240 | ~$640 |
| **Review total** | | | **~$820** | **~$330** | **~$1,150** |

The high estimate assumes workers take ~25% longer than expected. Bonuses are flat and unaffected by pace.

| | Expected | High (+25%) |
|--|----------|-------------|
| Review base pay | ~$820 | ~$1,025 |
| Review bonuses | ~$330 | ~$330 |
| **Total** | **~$1,150** | **~$1,355** |

# Data Collection: SEC Filing Q&A Data Collection

**Date:** April 2026

**Purpose:** This document describes how the main data collection (120 Q&A pairs collected, 100 delivered) is structured, including document selection, task set design, workflow, expected data output schema, and collection budget. This is a reference document for the project lead; worker-facing instructions are in `worker_facing/2.1_annotation_instructions.md` and `worker_facing/2.2_review_instructions.md`.

**Goal:** Generate 120 Q&As from the qualified worker pool; deliver the best 100 to the customer.

---

## Part 1: Document Selection

### Sectors

Five sectors were selected for maximum diversity in financial reporting structure, risk profile, and industry terminology. Technology and Financials appear three times each given their prevalence in SEC filings.

| Sector | Task Sets |
|--------|-----------|
| Technology | 3 (A01, A06, A11) |
| Healthcare | 2 (A02, A07) |
| Energy | 2 (A03, A08) |
| Financials | 3 (A04, A09, A12) |
| Industrials | 2 (A05, A10) |
| **Total** | **12** |

### Candidate Companies (5 per sector)

Companies were selected to vary by size (large/mid/small-cap) and financial health (profitable/struggling/growth-stage).

| Sector | Companies |
|--------|-----------|
| Technology | Apple, Intel, Palantir, Snowflake, Asana |
| Healthcare | UnitedHealth Group, HCA Healthcare, Teladoc Health, Hims & Hers, Agilon Health |
| Energy | ExxonMobil, Chevron, Viper Energy, Sunrun, Plug Power |
| Financials | JPMorgan Chase, Bank of America, Charles Schwab, Ally Financial, SoFi Technologies |
| Industrials | Caterpillar, Boeing, 3M, Watts Water Technologies, Haynes International |

The full list of companies with filing types, dates, and SEC links is in `2.0_all_companies.csv`. This file is also distributed to workers as a reference when sourcing additional filings for Category C questions.

---

## Part 2: Task Set Design

The project uses 12 pre-structured task sets (CSVs), one per annotator slot. Each task set covers 3 companies and contains 10 Q&A slots: 3 Category A, 3 Category B, and 4 Category C. Workers self-enter their annotator ID when they claim a task.

### Company Assignments

Companies were drawn from the sector pools to create meaningful overlap across sets in the same sector — building redundancy into the dataset while keeping each set distinct.

| Task Set | Sector | Company 1 | Company 2 | Company 3 |
|----------|--------|-----------|-----------|-----------|
| A01 | Technology | Apple (10-K) | Palantir (10-K) | Snowflake (10-Q) |
| A02 | Healthcare | UnitedHealth Group (10-K) | Teladoc Health (10-K) | Agilon Health (10-Q) |
| A03 | Energy | ExxonMobil (10-K) | Viper Energy (10-K) | Sunrun (10-Q) |
| A04 | Financials | JPMorgan Chase (10-K) | Charles Schwab (10-K) | Ally Financial (10-Q) |
| A05 | Industrials | Caterpillar (10-K) | Boeing (10-K) | Watts Water Tech. (10-Q) |
| A06 | Technology | Intel (10-K) | Apple (10-K) | Asana (10-Q) |
| A07 | Healthcare | HCA Healthcare (10-K) | Teladoc Health (10-K) | Hims & Hers Health (10-Q) |
| A08 | Energy | Chevron (10-K) | Plug Power (10-K) | Sunrun (10-Q) |
| A09 | Financials | Bank of America (10-K) | Charles Schwab (10-K) | SoFi Technologies (10-Q) |
| A10 | Industrials | Boeing (10-K) | 3M (10-K) | Haynes Intl. (10-Q) |
| A11 | Technology | Palantir (10-K) | Intel (10-K) | Asana (10-Q) |
| A12 | Financials | JPMorgan Chase (10-K) | SoFi Technologies (10-Q) | Charles Schwab (10-K) |

### Shared Companies Across Same-Sector Sets

| Sector | Sets | Shared Company |
|--------|------|----------------|
| Technology | A01, A06, A11 | Apple appears in A01 & A06; Intel in A06 & A11; Palantir in A01 & A11 |
| Healthcare | A02, A07 | Teladoc Health |
| Energy | A03, A08 | Sunrun (sole 10-Q in sector; appears in both sets) |
| Financials | A04, A09, A12 | Charles Schwab appears in all three; JPMorgan in A04 & A12; SoFi in A09 & A12 |
| Industrials | A05, A10 | Boeing |

---

## Workflow

The 12 task set CSVs are hosted in a shared Google Drive folder and edited directly in Google Sheets. Each row in a CSV is one task — annotation or review. Workers complete as many rows as they choose across any CSV, at their own pace.

**Annotation:** a worker opens any CSV, picks any row where `question` and `answer` are empty, and writes the Q&A for that row. Each CSV contains 10 rows: 3 Category A (one per company), 3 Category B (one per company), and 4 Category C (drawing on any relevant filings, including beyond the 3 in the CSV). Each row is pre-filled with the company, filing type, filing date, and `source_url` — workers use these to access the relevant SEC filing and write their Q&A. Full instructions are in `worker_facing/2.1_annotation_instructions.md`.

**Review:** a review task is also per-row. As soon as an annotation row is submitted, its review becomes available. Any qualified worker may review any completed row — they open the same Google Drive CSV, find any row where `question` and `answer` are filled in but `Rating (for reviewer)` is empty, and complete the review. Full instructions are in `worker_facing/2.2_review_instructions.md`.

---

## Expected Data Output

Each Q&A pair is recorded as one row in the task set CSV. Workers self-enter their annotator ID; all other pre-filled fields (sector, question_category, source company/filing info) are already populated.

| Field | Description |
|-------|-------------|
| `annotator_id` | Self-entered by worker when claiming the task |
| `sector` | Pre-filled (e.g., Technology) |
| `question_category` | Pre-filled (A, B, or C) |
| `question` | Worker-entered question text |
| `answer` | Worker-entered answer |
| `supporting_facts` | Worker-entered: source citations and evidence required to evaluate the answer without opening any filing |
| `additional_info` | Optional: any context needed to evaluate the answer (industry conventions, non-standard definitions, etc.) |
| `sources` | Pre-filled: company name(s); Cat A/B: one company; Cat C: all three companies in the task set |
| `filing_type` | Pre-filled: 10-K or 10-Q; Cat C: comma-separated for all three companies |
| `filing_date` | Pre-filled: filing date(s); Cat C: comma-separated for all three companies |
| `source_url` | Pre-filled: Google search link to SEC EDGAR filing; Cat C: "see above" |
| `time_spent` | Worker-entered: time spent on this row (e.g., "22 min") |
| `Rating (for reviewer)` | Reviewer-entered: 0, 1, or 2 |
| `Explanation (for reviewer)` | Reviewer-entered: rationale and bold corrections for any Rating 1 |

**Sample record:**

```
annotator_id:         A01
sector:               Technology
question_category:    B
question:             What was Apple's operating margin for fiscal year 2024,
                      and how did it change from fiscal year 2023?
answer:               Apple's operating margin for fiscal year 2024 was 31.5%,
                      calculated by dividing operating income ($123.2 billion) by
                      net sales ($391.0 billion). This is an increase from 29.8%
                      in fiscal year 2023 ($114.3 billion operating income /
                      $383.3 billion net sales). Neither figure is stated directly
                      in the filing; both require calculation from the consolidated
                      statements of operations.
supporting_facts:     Source: Apple 10-K FY2024, pgs. 33, 35
                      Total revenue (FY2024): $391.0B (pg. 33)
                      Operating income (FY2024): $123.2B (pg. 33)
                      Total revenue (FY2023): $383.3B (pg. 35)
                      Operating income (FY2023): $114.3B (pg. 35)
additional_info:      [none]
sources:              Apple
filing_type:          10-K
filing_date:          2025-10-31
source_url:           https://www.google.com/search?q=site%3Asec.gov+%22Apple+Inc%22+10-K+2025
time_spent:           24 min
```

---

## Data Collection Budget

**Rate: $20/hour.** Workers self-report hours; expected times below are provided as guidance.

Time estimates include document orientation (folded into per-question time). Annotation bonuses: Category B $2.50 per Q&A, Category C $5.00 per Q&A. Review bonuses: Category B $2.50 per review, Category C $5.00 per review. All bonuses are flat and unaffected by pace.

**Annotation (120 Q&As across 12 task sets):**

| Category | Count | Time per Q&A | Base pay | Bonuses | Total |
|----------|-------|-------------|----------|---------|-------|
| Category A | 36 | 20 min | ~$240 | — | ~$240 |
| Category B | 36 | 25 min | ~$300 | $2.50 × 36 = $90 | ~$390 |
| Category C | 48 | 30 min | ~$480 | $5.00 × 48 = $240 | ~$720 |
| **Annotation total** | | | **~$1,020** | **~$330** | **~$1,350** |

**Review (120 Q&As across 12 task sets):**

| Category | Count | Time per review | Base pay | Bonuses | Total |
|----------|-------|----------------|----------|---------|-------|
| Category A | 36 | 15 min | ~$180 | — | ~$180 |
| Category B | 36 | 20 min | ~$240 | $2.50 × 36 = $90 | ~$330 |
| Category C | 48 | 25 min | ~$400 | $5.00 × 48 = $240 | ~$640 |
| **Review total** | | | **~$820** | **~$330** | **~$1,150** |

The high estimate assumes workers take ~25% longer than the expected times. Bonuses are flat and not affected by pace.

| | Expected | High (+25%) |
|--|----------|-------------|
| Annotation base pay | ~$1,020 | ~$1,275 |
| Annotation bonuses | ~$330 | ~$330 |
| Review base pay | ~$820 | ~$1,025 |
| Review bonuses | ~$330 | ~$330 |
| **Total** | **~$2,500** | **~$2,960** |

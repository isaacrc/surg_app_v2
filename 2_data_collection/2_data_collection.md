# Data Collection: SEC Filing Q&A Data Collection

**Date:** April 2026

**Purpose:** This document describes how the main data collection (100 Q&A pairs) is structured, including document selection, annotator assignment logic, workflow, expected data output schema, and collection budget.

**Goal:** Generate 100 Q&As from expert annotators.

---

## Part 1: Document Selection

Our annotators were officially selected — now they need their documents. The question is which ones. Below we describe how these documents are selected.

### Sectors

Five sectors were selected for maximum diversity in financial reporting structure, risk profile, and industry terminology:

1. Technology
2. Healthcare
3. Energy
4. Financials
5. Industrials / Manufacturing

### Candidate Companies (5 per sector)

Companies were selected to vary by size (large/mid/small-cap) and financial health (profitable/struggling/growth-stage).

| Sector | Companies |
|--------|-----------|
| Technology | Apple, Intel, Palantir, Snowflake, Asana |
| Healthcare | UnitedHealth Group, HCA Healthcare, Teladoc Health, Hims & Hers, Agilon Health |
| Energy | ExxonMobil, Chevron, Viper Energy, Sunrun, Plug Power |
| Financials | JPMorgan Chase, Bank of America, Charles Schwab, Ally Financial, SoFi Technologies |
| Industrials | Caterpillar, Boeing, 3M, Watts Water Technologies, Haynes International |

Three of these companies will be assigned to each selected annotator. See the next section for details.

---

## Part 2: Annotator Assignment

### Sector Assignment

Each of the 5 sectors is assigned to exactly 2 annotators (one from the first cohort, one from the second):

| Sector | Annotator (Cohort 1) | Annotator (Cohort 2) |
|--------|---------------------|---------------------|
| Technology | Annotator 1 | Annotator 6 |
| Healthcare | Annotator 2 | Annotator 7 |
| Energy | Annotator 3 | Annotator 8 |
| Financials | Annotator 4 | Annotator 9 |
| Industrials | Annotator 5 | Annotator 10 |

### Company Assignment Within Sector

For each annotator, 3 companies are randomly sampled from the 5 in their sector. Of those 3 companies:
- 2 are assigned a 10-K filing
- 1 is assigned a 10-Q filing (filing type per company is randomly assigned)

Because 3 companies are drawn from 5, two annotators in the same sector will share some companies but not all — creating meaningful variation. Example:

- Annotator 1 (Tech): Apple (10-K), Snowflake (10-K), Palantir (10-Q)
- Annotator 6 (Tech): Apple (10-K), Intel (10-K), Snowflake (10-Q)
- → Apple appears in both; Palantir and Intel do not overlap

This structure produces:
- Multiple Q&A pairs per company from different annotators (redundancy)
- Variation in which filing type was used for the same company
- Hard (Category C) questions that span different company combinations across annotators

### Concrete Assignments (randomly drawn)

| Annotator | Sector | Company 1 | Company 2 | Company 3 |
|-----------|--------|-----------|-----------|-----------|
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

**Sector-pair overlap (shared company per pair):**

| Sector | Pair | Shared Company |
|--------|------|----------------|
| Technology | A01 & A06 | Apple |
| Healthcare | A02 & A07 | Teladoc Health |
| Energy | A03 & A08 | Sunrun (sole 10-Q in sector; both annotators receive it) |
| Financials | A04 & A09 | Charles Schwab |
| Industrials | A05 & A10 | Boeing |

Pre-filled assignment CSVs are located in `3_annotator_data/`: `A01_technology.csv`, `A02_healthcare.csv`, `A03_energy.csv`, `A04_financials.csv`, `A05_industrials.csv`, `A06_technology.csv`, `A07_healthcare.csv`, `A08_energy.csv`, `A09_financials.csv`, `A10_industrials.csv`.

---

## Workflow

Each annotator receives a task packet containing:
- `2.1_worker_facing_instructions.md`
- 3 assigned filings and submission template: company name, filing type, filing date, SEC page URL, and PDF

**Annotator deliverables (per submission):**

For each of the 3 assigned companies:
- 1 Category A Q&A
- 1 Category B Q&A

Plus, drawing on any relevant filings (including beyond the 3 provided):
- 4 Category C Q&As

**Total per annotator: 10 Q&A pairs**

---

## Expected Data Output

Each Q&A pair is recorded as one row in the annotator's CSV with the following fields:

| Field | Description |
|-------|-------------|
| `annotator_id` | Unique annotator identifier (e.g., A01–A10) |
| `sector` | Assigned sector (e.g., Technology) |
| `question_category` | A, B, or C |
| `question` | The question text |
| `answer` | Full, self-contained answer (includes Supporting Facts section) |
| `additional_info` | Optional: any context needed to evaluate the answer |
| `company_name` | Company name for each source filing |
| `filing_type` | 10-K or 10-Q |
| `filing_date` | Filing date |
| `sec_page_url` | URL to the SEC EDGAR HTML filing |
| `pdf_filename` | Name of the downloaded PDF |

**Sample record:**

```
annotator_id:       A01
sector:             Technology
question_category:  B
question:           What was Apple's operating margin for fiscal year 2023,
                    and how did it change from fiscal year 2022?
answer:             Apple's operating margin for fiscal year 2023 was 29.8%,
                    calculated by dividing operating income ($114.3 billion) by
                    net sales ($383.3 billion). This is a slight decline from
                    30.3% in fiscal year 2022 ($119.4 billion operating income /
                    $394.3 billion net sales). The margin figures are not stated
                    directly in the filing and require calculation from the
                    consolidated statements of operations.
additional_info:    [none]
source_documents:
  - company_name:   Apple Inc.
    filing_type:    10-K
    filing_date:    2023-11-03
    sec_page_url:   https://www.sec.gov/cgi-bin/browse-edgar?action=getcompany&CIK=AAPL
    pdf_filename:   Apple_10K_FY2023.pdf
```

---

## Data Collection Budget

**Rate: $20/hour**

Annotators spend 15 minutes reviewing each of their 3 assigned documents (getting oriented before writing), then 10 minutes composing each Category A question, 15 minutes per Category B question, and 20 minutes per Category C question (4 total). That adds up to a little over 3 hours of focused work per annotator.

Annotators receive base pay plus a $25 bonus if all 10 Q&As pass review on the first submission.

**Time breakdown per annotator:**

| Task | Calculation | Time |
|------|-------------|------|
| Document review | 15 min × 3 docs | 45 min |
| Category A Q&As | 10 min × 3 | 30 min |
| Category B Q&As | 15 min × 3 | 45 min |
| Category C Q&As | 20 min × 4 | 80 min |
| **Total** | | **200 min (~3h 20min)** |

**Phase budget:**

| Phase | What this covers | Workers | Hrs | Cost |
|-------|-----------------|---------|-----|------|
| Filing verification | Locate, verify, and record 10-K/10-Q filings for all 25 candidate companies [COMPLETE — sunk cost, not included in going-forward budget] | 1 | 6.25 | $125 |
| Annotation | 10 annotators × ~3.33 hrs each (200 min) | 10 | 33.3 | $667 |
| **Subtotal (going-forward)** | | | **33.3** | **~$667** |

# Qualification Project: SEC Filing Q&A Data Collection

**Date:** April 2026

**Purpose:** This document describes how qualified annotators are identified and screened for the project. It covers candidate sourcing, the paid qualification task, pass criteria, and the qualification budget.

**Goal:** Find 20 financially literate candidates, select 10 that pass the qualification assignment.

---

## Candidate Sourcing

This project requires annotators who read 10-K and 10-Q filings regularly as part of their professional or research work. Surge will conduct targeted outreach to experts within its network who match the following profiles:

**Ideal candidates:**

- **Equity research analysts** (sell-side or buy-side) — read 10-Ks as a core job function, write analytical Q&A-style research notes, experienced with cross-company comparison
- **Finance PhD students and postdocs** (corporate finance or accounting focus) — deep analytical training, experienced with financial statement analysis and SEC filings
- **CFA charterholders** in active analytical roles — demonstrated financial statement literacy by credential, with ongoing filing exposure
- **Former investment banking analysts** (2–4 years experience) — trained in financial statement analysis, now in roles with more availability
- **Management consultants** with significant due diligence exposure to public company filings

We are specifically looking for candidates who have spent meaningful time reading and analyzing SEC filings — ideally 100+ hours of direct, substantive engagement with 10-K and 10-Q documents. Surge's outreach should prioritize candidates who can demonstrate this through their professional or research background.

Candidates invited to apply proceed to a paid qualification task (below) before being admitted to the main project.

---

## Qualification Task

**Paid | ~60 minutes | $20/candidate**

Each candidate receives three pre-written Category C question-and-answer pairs and is asked to rate each response on a scale of 1–3. Each answer is well-written and sophisticated in tone but contains a subtle flaw — either an analytical error, an incomplete attribution, or a critical omission. After assigning a rating, the candidate must describe in approximately 150 words why the response received that grade, including identifying what was missed or incorrect.

This tests the skills most critical to this project: cross-document analytical reasoning, footnote literacy, and the ability to catch errors that are not immediately obvious.

**Rating scale:**

| Rating | Meaning |
|--------|---------|
| 3 | The response is accurate, complete, and self-contained |
| 2 | The response has a minor gap or omission; candidate must specify what is missing |
| 1 | The response contains a meaningful error or critical omission; candidate must explain why and describe what a correct answer would include |

---

## Evaluation Question 1

**Q:** How did Apple and Microsoft's revenue growth compare in fiscal year 2023, and what does the divergence reveal about their respective business models?

**A:** In fiscal year 2023, Apple reported net sales of $383.3 billion, a decline of 2.8% from $394.3 billion in FY2022, reflecting softening consumer demand for hardware products and foreign exchange headwinds. Microsoft reported revenue of $211.9 billion in fiscal year 2023, an increase of 6.9% from $198.3 billion in FY2022, driven by continued enterprise adoption of Azure cloud services and resilient demand for productivity software. This divergence illustrates a structural difference between the two companies: Apple's revenue base remains predominantly tied to hardware product cycles and consumer spending, while Microsoft's subscription and cloud model generates more durable, recurring revenue that proved resilient during a period of macroeconomic softening. [Sources: Apple 10-K FY2023, Microsoft 10-K FY2023]

**Supporting facts:**
- Apple's fiscal year ends on the last Saturday of September (FY2023: October 2022 – September 2023)
- Microsoft's fiscal year ends on June 30 (FY2023: July 2022 – June 2023)

**Expected rating: 1**

The answer is professionally written and directionally plausible, but the comparison is analytically invalid. Apple's fiscal year 2023 runs from October 2022 through September 2023. Microsoft's fiscal year 2023 runs from July 2022 through June 2023. These periods overlap but are not equivalent — they differ by a full quarter on each end. Treating both companies' "FY2023" as the same time window produces a misleading like-for-like comparison. A rigorous answer would either convert to calendar-year figures using quarterly data, or explicitly acknowledge the mismatch and its implications. A candidate who rates this above 1 without flagging the fiscal year discrepancy has failed to apply the cross-document scrutiny this project requires.

---

## Evaluation Question 2

**Q:** How do Apple and Palantir's effective tax rates compare to the U.S. statutory rate, and what drives the divergence in each case?

**A:** For fiscal year 2023, Apple reported an effective tax rate of approximately 14.7%, well below the 21% U.S. statutory corporate rate. Apple's tax footnotes attribute this primarily to the foreign-derived intangible income (FDII) deduction, earnings in lower-tax jurisdictions, and the federal R&D tax credit. Palantir reported an effective tax rate of approximately 3.2% for fiscal year 2023, also substantially below statutory rates, driven by federal and state R&D tax credits and deferred tax asset utilization. Both companies demonstrate that large technology firms can substantially reduce their effective tax burden through a combination of tax credits and international tax planning, though Apple's global footprint gives it more structural advantage. [Sources: Apple 10-K FY2023, Palantir 10-K FY2023]

**Supporting facts:**
- From Palantir's FY2023 tax footnote: excess tax benefits from stock-based compensation were the largest single contributor to the ETR reduction; R&D credits were a secondary contributor
- Palantir's SBC expense in FY2023 was approximately $491M on revenues of $2.2B (~22% of revenue)

**Expected rating: 2 or 3**

The answer correctly identifies Apple's tax drivers and the directional finding for both companies. However, it mischaracterizes the primary driver of Palantir's low effective tax rate. Palantir's ETR is dominated by excess tax benefits from stock-based compensation: when employees vest RSUs or exercise options, Palantir receives a tax deduction equal to the fair market value of the shares at that time. Given Palantir's substantial SBC expense and share price appreciation during this period, these excess tax benefits are the primary mechanism reducing its ETR — not R&D credits, which are a secondary contributor. This is disclosed in Palantir's tax footnote and is a well-known dynamic for high-growth technology companies with large equity compensation programs. The answer attributes the right conclusion (low ETR) to a plausible but incomplete explanation. A candidate who catches this and describes the SBC mechanism should receive a 2 (with correction noted) or 3 (if they also note that SBC-driven ETR benefits are inherently volatile and tied to stock price performance).

---

## Evaluation Question 3

**Q:** How do Plug Power and Sunrun's liquidity positions compare as of fiscal year 2022, and what do their disclosures reveal about near-term financial risk?

**A:** As of fiscal year 2022, Plug Power reported cash and cash equivalents of approximately $752 million with a current ratio above 2.0x, while Sunrun reported unrestricted cash of approximately $1.0 billion with a current ratio near 1.1x. While Sunrun's current ratio is lower, its established access to tax equity financing structures and asset-backed securitization markets provides diversified liquidity sources not fully reflected in its balance sheet. Both companies disclose ongoing capital needs in their risk factors, consistent with the capital-intensive nature of clean energy businesses. Plug Power's greater cash balance provides near-term flexibility, though both companies face structural reliance on external financing to fund growth. [Sources: Plug Power 10-K FY2022, Sunrun 10-K FY2022]

**Supporting facts:**
- Plug Power's FY2022 10-K includes an explanatory paragraph in the Report of Independent Registered Public Accounting Firm (KPMG) stating substantial doubt about the company's ability to continue as a going concern
- This paragraph appears in the auditor's report section — separate from management's risk factor disclosures — and represents an independent third-party assessment
- Sunrun's FY2022 10-K contains no such going concern qualification

**Expected rating: 2 or 3**

The answer accurately describes the balance sheet figures and risk factor language, but critically conflates two categorically different types of disclosures. Plug Power's FY2022 10-K includes a going concern qualification issued by its independent auditor (KPMG) — a formal statement that there is substantial doubt about the company's ability to continue as a going concern for the next twelve months. This appears in the independent auditor's report, a section separate from management's risk factor disclosures, and represents an independent third-party assessment rather than management-authored language. Sunrun's filings contain no such qualification. The answer treats both companies as having broadly similar risk profiles ("both companies flag ongoing capital needs") when they are in materially different positions. A going concern opinion is a significant regulatory and investor signal that the answer completely omits. A candidate who identifies this omission and explains the distinction between auditor-issued going concern qualifications and standard risk factor boilerplate should receive a 2 or 3.

---

## Pass Criteria

**Step 1 — Hard gate:** Candidates must rate Q1 as 1 and correctly identify the fiscal year mismatch as the reason. Any candidate who does not catch Q1 fails immediately, regardless of performance on Q2 or Q3.

**Step 2 — Catch at least one of Q2 or Q3:** Candidates who pass Q1 must also catch at least one of the following discrepancies:
- Q2: excess tax benefits from stock-based compensation as the primary driver of Palantir's low effective tax rate
- Q3: Plug Power's going concern qualification from its independent auditor

A rating of 1 on Q2 or Q3 is acceptable — what matters is whether the written explanation correctly identifies the specific flaw. A candidate who rates Q2 as 1 and names SBC excess tax benefits as the issue counts as catching it. A candidate who rates Q2 as 2 but gives only a vague explanation does not.

Catching both is not required to pass. Catching neither is a fail.

**Overall:** Written reasoning must be specific and analytical — not generic. Vague explanations ("the answer could be more complete") do not count as catching a discrepancy.

Following data collection, the project lead will review all submissions and score each candidate against the criteria above. The top 10 candidates by overall performance will be selected and admitted to the main project. In the event of ties or borderline cases, the project lead will use the quality and specificity of written reasoning as a tiebreaker.

Estimated qualification rate: 50% (recruit ~20 candidates to hire 10).

---

## Qualification Budget

**Rate: $20/hour**

| Phase | What this covers | Workers | Hrs | Cost |
|-------|-----------------|---------|-----|------|
| Qualification task | 20 candidates complete ~60-min evaluation task (paid); rate and critique 3 pre-written Q&As | 20 | 20 | $400 |
| Qual task review | Project lead scores 20 qual submissions (~15 min each) against pass/fail criteria | 1 | 5 | — |
| **Subtotal** | | | **25** | **~$400** |

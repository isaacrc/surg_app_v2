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

**A:** For fiscal year 2023, Apple reported an effective tax rate of approximately 14.7%, well below the 21% U.S. statutory corporate rate. Apple's tax footnotes attribute this primarily to the foreign-derived intangible income (FDII) deduction, earnings in lower-tax jurisdictions, and the federal R&D tax credit. Palantir reported an effective tax rate of approximately 3.2% for fiscal year 2023, also substantially below statutory rates, driven by a combination of tax credits and deductions related to its compensation structure. Both companies demonstrate that large technology firms can substantially reduce their effective tax burden through a combination of tax planning and compensation-related tax treatment, though Apple's global footprint gives it more structural advantage. [Sources: Apple 10-K FY2023, Palantir 10-K FY2023]

**Supporting facts:**
- From Palantir's FY2023 tax footnote: excess tax benefits from stock-based compensation were the largest single contributor to the ETR reduction; R&D credits were a secondary contributor
- Palantir's SBC expense in FY2023 was approximately $491M on revenues of $2.2B (~22% of revenue)

**Expected rating: 2 or 3**

The answer is passable — it reaches the right conclusion and the numbers are accurate. But "tax credits and deductions related to its compensation structure" is vague. Palantir's tax footnote explicitly identifies excess tax benefits from stock-based compensation as the primary driver of its low ETR: when employees vest RSUs or exercise options, Palantir receives a tax deduction equal to the fair market value of those shares, which significantly reduces its taxable income. Given Palantir's SBC expense of approximately $491M on $2.2B in revenue (~22% of revenue), this is the dominant mechanism — not a generic tax planning strategy. An answer that stops at "compensation-related deductions" without naming this mechanism is glossing over the most important detail. A candidate who flags this vagueness and explains the SBC excess tax benefit mechanism should give it a 2; one who doesn't notice the imprecision may give it a 3.

---

## Evaluation Question 3

**Q:** How do Plug Power and Sunrun's liquidity positions compare as of fiscal year 2022, and what do their disclosures reveal about near-term financial risk?

**A:** As of fiscal year 2022, Plug Power reported cash and cash equivalents of approximately $752 million with a current ratio above 2.0x, while Sunrun reported unrestricted cash of approximately $1.0 billion with a current ratio near 1.1x. While Sunrun's current ratio is lower, its established access to tax equity financing structures and asset-backed securitization markets provides diversified liquidity sources not fully reflected in its balance sheet. Plug Power disclosed going concern uncertainty in its FY2022 filing, noting substantial doubt about its ability to continue as a going concern — a materially weaker position than Sunrun, whose filing contains no equivalent disclosure. This divergence signals meaningfully different levels of near-term financial risk between the two companies. [Sources: Plug Power 10-K FY2022, Sunrun 10-K FY2022]

**Supporting facts:**
- Plug Power's FY2022 10-K includes an explanatory paragraph in the Report of Independent Registered Public Accounting Firm (KPMG) stating substantial doubt about the company's ability to continue as a going concern
- This paragraph appears in the auditor's report section — separate from management's risk factor disclosures — and represents an independent third-party assessment
- Sunrun's FY2022 10-K contains no such going concern qualification

**Expected rating: 2 or 3**

The answer correctly identifies the going concern divergence and its significance — the main finding is right. The gap is in how the disclosure is characterized. Plug Power's going concern language appears in the Report of Independent Registered Public Accounting Firm (KPMG), not in management's risk factor disclosures. This is a meaningful distinction: an auditor-issued going concern qualification is a formal, independent third-party assessment with specific regulatory implications, categorically different from management's own characterization of financial risk. The answer's vague reference to Plug Power "disclosing" going concern uncertainty doesn't convey where this language appears or why that source matters. A candidate who catches this and explains the auditor vs. management distinction should give it a 2; one who accepts the answer as sufficiently complete may give it a 3.

---

## Pass Criteria

**Step 1 — Hard gate:** Candidates must rate Q1 as 1 and correctly identify the fiscal year mismatch as the reason. Any candidate who does not catch Q1 fails immediately, regardless of performance on Q2 or Q3.

**Step 2 — Catch at least one of Q2 or Q3:** Candidates who pass Q1 must also catch at least one of the following discrepancies:
- Q2: excess tax benefits from stock-based compensation as the primary driver of Palantir's low effective tax rate
- Q3: Plug Power's going concern qualification from its independent auditor

The expected rating for Q2 and Q3 is 2 — the answers are passable but gloss over a meaningful detail. A candidate who rates either question as 2 and correctly identifies the specific gap counts as catching it. A rating of 3 means the candidate missed the gap entirely. A candidate who rates either question as 2 but gives only a vague explanation does not count as catching it.

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

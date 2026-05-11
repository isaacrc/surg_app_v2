# Revision Notes

Tracking changes made in response to reviewer feedback.

---

## Feedback Point 1 — Support modularity in data structure

> "Where applicable, it's useful to separate components like supporting facts from final answers, rather than blending things together. Keeping things modular helps with flexibility downstream."

### Changes

**`2_data_collection/2.1_worker_facing_instructions.md`**
- Added a dedicated `## Supporting Facts` section, placed between the difficulty-level task examples and `## Getting Started`. This section opens with an explanation of the component's purpose, then details the per-category requirements (Easy / Medium / Hard).
- Condensed Quality Standards item 2 ("Self-contained answers with Supporting Facts") to a single cross-reference pointing to the new section, removing the duplicated per-category detail.

**`4_quality_control/4_quality_assurance.md`**
- Updated the reviewer self-containedness criterion from a vague one-liner to an explicit reference: "are the Supporting Facts sufficient — per the criteria in 2.1 — for a finance-literate reader to evaluate the submission without opening any filing?"

**`3_annotator_data/A01_technology.csv` — `A10_industrials.csv` (all 10 files)**
- Added a `supporting_facts` free-text column between `answer` and `additional_info` in all annotator submission CSVs, making Supporting Facts a structurally distinct field rather than a component embedded within the answer.

---

---

## Feedback Point 2 — Expand on the task revisions process

> "We like your idea to allow edits to tasks that contain fixable issues and we would like to see some more detail around this process, including whether reviewers have the ability to make edits in order to save on time."

### Changes

**`2_data_collection/2.1_worker_facing_instructions.md`**
- Expanded the Rating 1 paragraph into a full `### Revising the Submission` subsection in Task 2.
- Reviewers must: (1) explain why the submission is insufficient, (2) implement a correction directly in the record using bold text, (3) provide written rationale.
- Category A/B: reviewer edits go to project lead for acceptance — clear factual issues with a verifiable right answer.
- Category C: reviewer edits are sent to the original annotator for one paid round of response before the project lead decides — synthesis questions are interpretive and the original annotator may have spent more time on the specific filings.
- Added that reviewers receive all referenced documents (including extra Cat C filings) to verify claims directly.

**`4_quality_control/4_quality_assurance.md`**
- Removed Annotator Notice section (redundant with Overview).
- Restructured Review Structure section: removed the separate Rating Scale and Disposition Logic tables; replaced with prose paragraphs describing Rating 2, Rating 0, Rating 1 Cat A/B, and Rating 1 Cat C (rebuttal + arbitration by third reviewer) flows.
- Added arbitration mechanism for Cat C disputes the project lead cannot resolve: both arguments forwarded to a third uninvolved reviewer for a binding vote.
- Moved "Estimated time per reviewer" table to the QA Budget section.
- Removed the sentence about reviewers receiving all referenced documents from Review Structure (document access info now lives in 2.1 Factual accuracy bullet).
- Updated reviewer instructions paragraph to reference 2.1 for the full revision process.

**`2_data_collection/2.1_worker_facing_instructions.md`**
- Added rebuttal/payment notice to the opening payment paragraph: annotators informed they may be contacted for a rebuttal on Rating 1 items and will be paid for that time.
- Removed "You will not know whose work you are reviewing." (unnecessary).
- Folded document access info into the Factual accuracy bullet in the review checklist.
- Removed the "The process then differs by category" block from Revising the Submission — reviewers do not need to know internal disposition details.

---

---

## Additional revisions (feedback pt. 2 cont. + structural cleanup)

**`3_annotator_data/A01–A10` (all 10 CSVs)**
- Removed source_2 and source_3 column sets (source info for additional filings now captured in supporting_facts).
- Removed source_4_plus_notes column.
- Added `rating` and `explanation` columns for reviewer use.
- Final schema: annotator_id, sector, question_category, question, answer, supporting_facts, additional_info, source_1_company, source_1_filing_type, source_1_filing_date, source_1_sec_url, source_1_pdf_filename, rating, explanation.

**`2_data_collection/2.1_worker_facing_instructions.md`**
- Added anchor links and a "Jump to" nav bar in "Your Tasks at a Glance".
- Updated rating table to 3 columns: Meaning + Rating 1 examples (non-exhaustive), with per-category examples for Cat A/B/C.
- Expanded Hard Q&A review bullet to include: verify each company-level claim has a Supporting Facts entry; evaluate whether synthesis is logically supported.
- Updated deliverables list to reference supporting_facts column; replaced source_4_plus_notes reference with supporting_facts citations.
- Added "Example Reviewed Rows" subsection after Revising the Submission, showing a Rating 2 and Rating 1 example row.

**`4_quality_control/4_quality_assurance.md`**
- Added Step 1 / Step 2 / Step 3 headers within Review Structure.
- Updated rating table to match 2.1 (3 columns with per-category Rating 1 examples).
- Expanded Category C reviewer instruction to match updated Hard Q&A bullet in 2.1.

---

---

## Additional revisions (reviewer checklist restructure)

**`2_data_collection/2.1_worker_facing_instructions.md` and `4_quality_control/4_quality_assurance.md`**
- Removed "Factual accuracy" top-level bullet and category-specific "For Medium / For Hard Q&As" bullets.
- Replaced with two explicit parallel sections: **Self-Containedness** (is the required evidence present?) and **Accuracy** (is what's present correct?), each with per-category sub-bullets.
- Easy accuracy check is the one place reviewers are expected to open the source document; Medium and Hard accuracy checks run from Supporting Facts alone.
- Rating table condensed back to 2 columns in both docs; examples now live in the checklist where they're actionable.
- Added document access notice as intro sentence to 2.1 reviewer checklist.

**`3_annotator_data/A01–A10` (all 10 CSVs)**
- Renamed `rating` → `Rating (for reviewer)` and `explanation` → `Explanation (for reviewer)` to avoid annotator confusion.

---

---

## Additional revisions (Step 2/3 rewrite, checklist cleanup)

**`4_quality_control/4_quality_assurance.md`**
- Step 2: Reordered disposition paragraphs — Rating 2, Rating 1 A/B, Rating 1 C, Rating 0 (rating 0 moved to end; rejections expected to be rare; now follows same rebuttal process as Cat C).
- Step 3: Rewrote arbitration section — persistent conflict (annotator rejects change after first round, for rating 0 or 1) goes to project lead; contested item may be dropped from final 100 and replaced from reserve pool; if conflict is widespread, second arbitration round initiated with third reviewer from uninvolved sector pair voting on which argument is most valid.
- Accuracy Hard bullet: removed "flag if a filing is too old or unverifiable" (redundant with the filing date confirmation already in that bullet).
- Removed "Source citation" standalone bullet (redundant with self-containedness and accuracy checks).
- Added hyperlink to 2.1 — Revising the Submission on the "See 2.1" reference.

---

*Remaining feedback points to be addressed: 3, 4*

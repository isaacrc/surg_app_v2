# Revision Notes

High-level summary of all changes made in v2, organized by reviewer feedback and structural redesign.

---

## Feedback Point 1 — Support modularity in data structure

> "Where applicable, it's useful to separate components like supporting facts from final answers, rather than blending things together. Keeping things modular helps with flexibility downstream."

`supporting_facts` is now a structurally distinct column in the CSV schema, separate from `answer` and `additional_info`. The annotation instructions include a dedicated Supporting Facts section with explicit per-category requirements: page citation only for Easy; all calculation inputs with page numbers for Medium; per-company cited facts or quoted language with filing and page for Hard, with absent disclosures documented. The `additional_info` column is also explained as its own distinct field — evidence vs. context.

---

## Feedback Point 2 — Expand on the task revisions process

> "We like your idea to allow edits to tasks that contain fixable issues and we would like to see some more detail around this process, including whether reviewers have the ability to make edits in order to save on time."

Reviewers now implement corrections directly in the Google Sheet row using bold text — no back-and-forth with the annotator for Easy and Medium items. Those corrections go straight to the project lead to accept, keeping the process fast for the common case. Hard questions are treated differently: an annotator may reasonably disagree with a reviewer's interpretation of cross-document synthesis, so they receive one paid rebuttal round before the project lead makes a final call. Anything still unresolved after that goes to a third-reviewer arbitration step. A concrete Rating 1 example was added to the reviewer instructions so the correction format is easy to follow in practice.

---

## Feedback Point 3 — Ensuring enough task count in collection

> "Often when running a project, it's a good idea to over-collect a small amount of extra tasks such that removal of poor tasks won't require reopening another collection process. We'd suggest implementing this in your project based on your best intuition."

Collection target was raised from 100 to 120 Q&As — a 20-item buffer (~20%). If a Q&A is rejected after the rebuttal process, or a conflict cannot be resolved in arbitration, the item can simply be dropped and replaced from the reserve pool without reopening collection. The buffer size was chosen to cover a realistic worst-case rejection rate given the expert annotator pool. This is reflected throughout the project: `0_project_summary.md` explains the 120/100 split upfront, and `3_quality_assurance.md` references the reserve pool explicitly in the arbitration step.

---

## Feedback Point 4 — No minimums, no deadlines; flexible task structure

> "Workers do not have to submit any minimum number of tasks on the platform, nor do they have to adhere to any deadlines. They can work on tasks as they please and are not obligated to work on any project, even ones they passed qualifications for. You might want to explore other ways that you could achieve your target category and sector split that don't involve requiring workers to submit a set number of tasks in a CSV by a deadline."

The fixed annotator assignment model — where each worker was responsible for completing a full set of 10 Q&As — was replaced with an open, per-row task pool. Workers claim individual rows at their own pace with no minimums and no deadlines. The target category split (30/30/40 across Category A, B, C) and sector diversity are preserved structurally rather than through worker obligations: each task set CSV is pre-populated with exactly 3 Category A, 3 Category B, and 4 Category C rows spanning a single sector, so the correct ratio holds as long as enough rows are completed across the pool — regardless of which workers complete them or how many each worker does. This is documented in `2_data_collection/project_lead/2_data_collection.md` and reflected in the worker-facing instructions in `2.1_annotation_instructions.md`.

---

## v2 Structural Redesign

### Open self-paced task pool

The fixed annotator assignment model (one annotator per set of 10) was replaced with an open, per-row task pool. Each row in a task set CSV is one claimable task — annotation or review. Any qualified worker may pick up any unclaimed row across any CSV at their own pace, with no minimums and no deadlines. Workers self-enter their annotator ID when they take a row.

### CSV schema overhaul

The source columns were consolidated from a multi-column structure into four fields: `sources`, `filing_type`, `filing_date`, `source_url`. For Category C rows, all three companies in the task set are listed comma-separated across those fields; `source_url` reads "see above." A `time_spent` column was added for per-row payment tracking. The PDF filename column was removed — workers download filings for their own reference but are not required to upload anything.

### Review model

Sector-paired blind reviewer assignment was removed. Review is now open: any qualified worker reviews any completed row. Category B reviews now earn a $2.50 per-row bonus (matching the annotation bonus). The v1 performance bonus ($25 for all 10 Q&As rated 2 on first submission) was removed — it doesn't apply to the per-row model.

### Google Drive / Google Sheets workflow

Task set CSVs are hosted on Google Drive and edited directly in Google Sheets. The `3_annotator_data/` directory was removed from the git repo and added to `.gitignore`; the live task sets live on Drive.

### Directory restructure

`worker_facing/` and `project_lead/` subdirectories were added to both `1_annotator_qualification/` and `2_data_collection/`, separating worker-facing documents from internal ones. `4_quality_control/` was renumbered to `3_quality_control/` and `4_quality_assurance.md` to `3_quality_assurance.md`. READMEs were removed from `1_annotator_qualification/` and `3_quality_control/`.

### Document updates

**`0_project_summary.md`** — Budget updated to include Category B review bonus; timeline section added (~6 weeks total); file path references updated to reflect new directory structure; PNG reference corrected.

**`1_annotator_qualification/worker_facing/1.1_qual_candidate_instructions.md`** — Overview updated with a project description and casual tone matching 2.1, without revealing that the qualification Q&As contain flaws.

**`2_data_collection/worker_facing/2.1_annotation_instructions.md`** — Full rewrite: Hello opening, LLM fine-tuning context, per-row Getting Started steps, Google Drive link, updated pay table with per-row bonuses, `additional_info` section, sample completed record.

**`2_data_collection/worker_facing/2.2_review_instructions.md`** — Full rewrite: Hello opening, LLM fine-tuning context, per-row Getting Started steps, merged step 2+3, Rating 1 correction example, updated pay table.

**`2_data_collection/project_lead/2_data_collection.md`** — Workflow section rewritten to frame each row (not each set) as the unit of work; Google Drive hyperlink added.

**`3_quality_control/3_quality_assurance.md`** — Full rewrite: open per-row review model, sector-pairing removed, updated disposition logic, updated budget with Category B review bonus, corrected file path references.

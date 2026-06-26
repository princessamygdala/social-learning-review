# Human QA — Verification of Extracted Studies

The human-checking layer for the systematic review. It covers **all 484 studies**
in the extraction set (`data/clean/review_categorized_new_extractions.csv`), which
is 40 more than the **444** currently published on the website. Those 40 were
dropped downstream (duplicates, inaccessible full text, automated-agent or
borderline-eligibility cases); here they are surfaced with a flag for review
rather than silently removed.

## How a reviewer works

1. Open the study's readable file in `study_files/` (one markdown file per study,
   all fields stacked vertically — this is what you **read from**).
2. Check each field against the actual paper.
3. Record verdicts in the check-sheet CSVs below (what you **record into**).

Everything is keyed on `study_id` (e.g. `a44cda9eb501547e6_s1`), which joins the
read files, the check-sheets, the website, and the source extraction CSVs.

---

## `study_files/` — one readable file per study (the "read-from" source)

484 markdown files named `<Citation>__<study_id>.md`, plus `INDEX.csv`. Each file
stacks every field vertically under sections:

- Identification, Computational level, Algorithmic level, Implementation level,
  Quality, Context flags, QC / extraction notes — the hand-extracted fields.
- **Taxonomy / categorization** — the active (truthy) binary codes only
  (tax_*, rr_*, pop_*, pharma_*, spec_*), grouped, so the ~225-column
  categorization layer is checkable without a wall of zeros. The reviewer
  confirms the active codes are right *and* that nothing is missing.

Files for the 40 dropped studies show `on_website: NO` with a `why_not_on_website`
line; their taxonomy layer is not generated (those columns exist only for
published studies).

`INDEX.csv` lists every file with `study_id, citation_short, on_website, file`.

---

## `eligibility_decisions.csv` — one include/exclude decision per study (484 rows)

| Column | Filled by | Meaning |
|---|---|---|
| `study_id`, `paper_id`, `citation_short`, `year` | machine | Identifiers |
| `on_website` | machine | `YES` (published) / `NO` (dropped — see dropped review) |
| `eligibility_flagged` | machine | `YES` if the extraction raised a flag, else `NO` |
| `eligibility_flag_reason` | machine | The extraction's flag reason (blank if none) |
| `human_decision` | **human** | `include` / `exclude` / `uncertain` |
| `human_rationale` | **human** | Why — required for `exclude` / `uncertain` |
| `reviewer`, `date_checked` | **human** | Initials, YYYY-MM-DD |
| `status` | **human** | `pending` → `done` |

The extraction protocol never auto-excludes; it only flags. This file is where the
human exclusion decision is actually recorded.

---

## `field_verification.csv` — every field of every study checked (484 rows)

Wide check-sheet. The reviewer reads the study's `study_files/` record, ticks the
row as checked, and logs **only** the fields that are wrong.

| Column | Filled by | Meaning |
|---|---|---|
| `study_id`, `paper_id`, `citation_short`, `year` | machine | Identifiers |
| `on_website` | machine | `YES` / `NO` |
| `study_focus_short` | machine | Short label to identify the row |
| `row_checked` | **human** | `Y` once the whole record is reviewed |
| `fields_with_errors` | **human** | Semicolon list of wrong field names (blank = all correct) |
| `corrections` | **human** | `field=new value; field2=new value` for each error |
| `reviewer_note` | **human** | Free-text (ambiguity, follow-up) |
| `reviewer`, `date_checked` | **human** | Initials, YYYY-MM-DD |
| `status` | **human** | `pending` → `done` |

Field names in `fields_with_errors` / `corrections` must match the schema column
names (e.g. `winning_model`, `coordinates_peak`, or a taxonomy code like
`tax_topic_trust`).

---

## `dropped_studies_review.csv` — double-check the 40 drops (40 rows)

Focused list of every study in the extraction but not on the website, so each drop
can be confirmed or reversed.

| Column | Filled by | Meaning |
|---|---|---|
| `study_id`, `paper_id`, `citation_short`, `year` | machine | Identifiers |
| `recorded_drop_reason` | machine | The eligibility flag / drop reason (18 have none recorded — flagged as "likely duplicate/superseded; confirm") |
| `human_decision` | **human** | `keep_dropped` / `reinstate` / `uncertain` |
| `human_rationale` | **human** | Why |
| `reviewer`, `date_checked`, `status` | **human** | Initials, date, `pending` → `done` |

Studies marked `reinstate` should be added back to the website data with an
appropriate eligibility flag (not silently restored).

---

## Provenance & regeneration

- Read files and check-sheets generated from
  `data/clean/review_categorized_new_extractions.csv` (484 studies, source of
  truth for hand-extracted fields) merged with
  `social-learning-review-public/studies.json` (444 published, source of the
  taxonomy/categorization columns).
- **Do not regenerate after checking has started** — the generator overwrites the
  empty human columns. Re-run only to refresh machine columns on an untouched
  scaffold.
- When checking is complete, logged `corrections` are applied back to the master
  extraction CSVs and the website data regenerated; `reinstate` decisions add
  dropped studies back. These QA files stay in version control as the permanent
  record of what was checked and changed.

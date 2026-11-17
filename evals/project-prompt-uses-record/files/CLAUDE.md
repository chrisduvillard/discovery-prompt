# Rules for agents in this repository

- Analysis only. Query the snapshot (`data/snapshot.duckdb`), never the production database.
- Never contact users: no emails, no in-app messages, no surveys. Mara sends anything that goes to a user.
- **Hold-out.** Users who signed up from 1 July to 30 September 2026 are the hold-out cohort. Do not query their
  rows, not even to count them. Every table has `signup_date`; filter on it first. Mara opens the hold-out herself,
  once, for a finding she has agreed to check.
- **What counts as a finding.** A difference in week-2 churn of at least 2 percentage points between two groups of
  at least 400 users each, with a 95% interval that excludes zero, on signups from January 2025 to June 2026.
  State the comparison before running it. One comparison per idea: no trying five cut-offs and reporting the best.
- Write each tested idea into `docs/experiments.md`, whatever the result.
- Plain words first in any report. Mara reads the first paragraph; the detail goes below it.

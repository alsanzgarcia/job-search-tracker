# job-search-tracker

State for the "Daily PKPD/Pharma Job Search" Claude Code routine.

## Files

- **companies.md** — list of company career page URLs the routine should crawl
  in addition to general job-board search. Add a line any time; picked up on
  the next run automatically. No restart needed.
- **sent_jobs.json** — append-only log of jobs already emailed. Each entry:
  ```json
  {
    "title": "Pharmacometrician",
    "company": "Idorsia",
    "location": "Allschwil, Switzerland",
    "url": "https://...",
    "date_sent": "2026-09-08"
  }
  ```
  The routine reads this before searching, skips anything already listed, and
  appends new matches after sending the email — then commits and pushes.

## Editing

Just edit `companies.md` in this repo (web UI or a clone) whenever you find a
new company worth tracking. Don't edit `sent_jobs.json` by hand unless you're
fixing a mistake — the routine manages it.

# Cybersecurity Notes

Single HTML file of software development cybersecurity notes, tracked in git
instead of manually-numbered copies. History was backfilled from 8 versioned
`cybersecurity-notes-vN.html` exports on 2026-09-01 — `git log` is a real,
backdated timeline (matching each file's creation time), not just a migration
commit.

## Files

- `index.html` — the one live, tracked file (named `index.html`, not
  `cybersecurity-notes.html`, so GitHub Pages serves it at the repo's root
  URL). Never fork this into `cybersecurity-notes-v9.html` etc. — commit
  changes to it directly.
- `update-notes.sh` — run after downloading a fresh export straight into this
  folder (as `cybersecurity-notes-vNN.html` or similar). It diffs it against
  the tracked file, commits, pushes to GitHub, and deletes the downloaded copy.
- `poster-cybersecurity-sac.html` / `.pdf` — double-sided A4 SAC revision
  poster (Weeks 1–4). Type scales from the single `--fs` custom property in
  `:root`; every other size is an `em`, so raising `--fs` is the only knob
  needed to trade content for legibility. At 5.1pt both sides fit one page
  each. Print the PDF, not the HTML.
- `revision-cybersecurity-weeks1-4.html` / `.pdf` — the study version of the
  same content in note form, two columns to the page at 8pt, ~9 A4 pages,
  with recall prompts collected at the end. Includes Week 1 Lesson 1, which
  the poster omits entirely. An earlier 31-page long-prose edition of this
  file is in git history (commit 3e396e9) if the fuller wording is ever
  wanted back.
  Layout notes: the two columns are CSS multicol on `.flow`. Don't put
  `column-span:all` elements inside it — Chromium duplicates the spanner per
  fragment and emits a near-blank trailing page (this is why the footer sits
  outside `.flow` and the case studies are cards, not one wide table). Don't
  put `break-inside:avoid-column` on `.lesson` either; it strands half-empty
  columns.

## Workflow

- Normal edit: modify `index.html`, then `git add index.html
  && git commit -m "..." && git push`.
- New export downloaded: run `update-notes.sh` instead of doing it by hand.
- Do not add a `Co-Authored-By: Claude` trailer to commit messages in this repo.

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

## Workflow

- Normal edit: modify `index.html`, then `git add index.html
  && git commit -m "..." && git push`.
- New export downloaded: run `update-notes.sh` instead of doing it by hand.
- Do not add a `Co-Authored-By: Claude` trailer to commit messages in this repo.

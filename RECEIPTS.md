# Brotprobe receipts

Till receipts: newest first, one per change a reader can see and one per correction. Each is short, and enough to
trace the change back to its commit.

- **change**: what changed, who asked for it, the check that proves it (and the planted fault that check catches), and
  the commit.
- **correction**: what was claimed before, what was wrong with it, and what made someone look.

## 2026-10-21 · change · wording review integrated

- **What:** README only: the region, ray, claim and recipe paragraphs now say what a finite test does and does not show.
  Added: "neither" and invalid samples are counted; staying inside for the budget is not membership, and only a proven
  escape bound certifies escape; a ray report states the march spacing, refinement tolerance and crossing rule, and a
  finite march can miss a thin pair of crossings; a claim is "proved" only with a proof or certificate and its source;
  the recipe lists the map and brackets, convention, construction, budget, threshold, grid order, seed, backend and block
  hashes, repeats under a declared tolerance, and the Brotoscope join is marked planned until a shared schema and
  code exist. The status line now says no command is delivered.
- **Asked:** Doug Bristor ("do the brotprobe wording"), on caro's review of the public README of 2026-10-20 (TC 6e89a51a60).
  Caro supplied the replacement paragraphs; git integrated them, shortened to fit the README.
- **Checked by:** caro's review of the earlier text (the text above is git's edit of it, not yet re-read by caro).
  Mechanical check: each of the review's six corrections was matched to a sentence in the new README, and the
  README was scanned for local paths and addresses (none). This is a prose change: there is no code, so no planted
  fault applies. No reader trial has been run, so the README is not shown to teach a newcomer.

## 2026-10-13 · change · repository created

- **What:** intent only: README, receipts and licence, no code.
- **Asked:** Doug Bristor: the command-line half of the Brotoscope idea is a testing kit that produces result data,
  not renders, so it gets its own repository. Named `brotprobe` by Doug Bristor.
- **Checked by:** the README reuses the finite-test wording that caro reviewed for the Brotoscope (finite no-escape
  tests, not membership; recipes carry declared settings). No other review yet.

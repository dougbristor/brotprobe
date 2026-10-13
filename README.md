# Brotprobe

**Status: intent only. There is no code here yet.** This repository holds the name and the plan for Brotprobe, a
command-line kit for testing Bristorian and quaternion fractals. It produces result data, not pictures.

**Website: [bristorbrot.org](https://bristorbrot.org)** · Main code: [dougbristor/bristorbrot](https://github.com/dougbristor/bristorbrot)
(reusable algebra blocks and the simple player) · Its viewing twin: [dougbristor/brotoscope](https://github.com/dougbristor/brotoscope)

## What it is for

The Brotoscope is for looking. Brotprobe is for measuring. It asks the same questions with no screen, and answers
them with numbers that can be checked, compared and repeated.

- **Classify a region.** Count the samples in a box or a section by finite no-escape tests at a stated iteration
  budget: both orbits stay inside the escape radius (shared), only the Bristorian orbit does (B-only), or only the
  quaternion orbit does (Q-only). These are finite tests, not proofs that a point belongs to the set.
- **Measure along a ray.** Find where a ray crosses the edge of a set, and how far inside or past that edge a chosen
  point sits, for example a Julia parameter measured along its own ray in the parameter set.
- **Scan.** Sweep a parameter, a section or a region, and write the results as a table.
- **Check a claim.** Recompute a property claimed for the algebra or its sets and report it with its status: proved,
  measured or heuristic.
- **Measure a view.** Take the recipe of a view from the Brotoscope or the player, and measure what it shows.

## What it produces

- **Result data:** plain tables (CSV or JSON). Brotprobe makes no renders; pictures belong to the Brotoscope and
  the player.
- **A recipe with every result.** The recipe records everything that produced the number: the map, section,
  parameter, iteration budget, sample grid and the version of the blocks used. Running the recipe again with the
  same version of the blocks reproduces the result, and the same recipe opens the view in the Brotoscope, so a
  number can be looked at and a view can be measured.

## How it will be built

- **Algebra comes from the blocks.** The plan is for Brotprobe to use the conformance-tested blocks from
  [dougbristor/bristorbrot](https://github.com/dougbristor/bristorbrot) (`core/`) rather than its own copies of the
  products, so a change to the algebra happens once, in the block, with its tests.
- **A result is a test only when it can fail.** Each command arrives with a check that passes as shipped and fails
  when a planted fault is switched on, such as the wrong product or a dropped term.
- **Every result says how far to trust it.** A minimum found over many samples is a measurement, not a proof, and is
  labelled as one.
- **Current first, history second.** The README describes what the kit does now. [RECEIPTS.md](RECEIPTS.md) records
  every change and every correction, newest first, with what proved it.

## Bristorian is not quaternion

They share the symbols i, j and k but are different algebras. Bristorian numbers (imordials) have ranked imaginary
units, with `i·j = j` and `j·i = −i`. Their product depends on order and on brackets. Quaternions depend on order
only. Brotprobe exists to measure exactly where that difference changes the sets.

## Licence

Code is [MIT](LICENSE). Copyright (c) 2026 Doug Bristor.

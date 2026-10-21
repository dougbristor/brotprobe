# Brotprobe

**Status: intent only. There is no code here yet.** This repository holds the name and the plan for Brotprobe, a
command-line kit for testing Bristorian and quaternion fractals. It produces result data, not pictures. Everything
below describes what is planned; no command is delivered.

**Website: [bristorbrot.org](https://bristorbrot.org)** · Main code: [dougbristor/bristorbrot](https://github.com/dougbristor/bristorbrot)
(reusable algebra blocks and the simple player) · Its viewing twin: [dougbristor/brotoscope](https://github.com/dougbristor/brotoscope)

## What it is for

The Brotoscope is for looking. Brotprobe is for measuring. It asks the same questions with no screen, and answers
them with numbers that can be checked, compared and repeated.

- **Classify a region.** Count the samples in a box or a section at a stated iteration budget and radius threshold:
  both orbits stay inside (shared), only the Bristorian orbit does (B-only), only the quaternion orbit does (Q-only),
  or neither does. Samples that are invalid or could not be computed are reported separately. Staying inside for the
  budget is a finite test: it does not show that a point belongs to the set. Only a proven escape bound, under its
  stated conditions, certifies that an orbit escapes.
- **Measure along a ray.** Locate the sampled transitions along a ray in a declared finite no-escape test, refine
  their brackets, and report where a chosen point sits relative to them, for example a Julia parameter measured
  along its own ray in the parameter set. The march spacing, the refinement tolerance and the rule for choosing
  among crossings are stated with the result. A finite march can miss a thin pair of crossings between two
  samples, so it does not by itself find every crossing of the edge, or prove that a point is inside or outside.
- **Scan.** Sweep a parameter, a section or a region, and write the results as a table.
- **Check a claim.** Recompute a numerical consequence of a claim for the algebra or its sets and report it with
  its domain, its arithmetic and its tolerance, and the claim's status: proved, measured or heuristic. A claim is
  labelled proved only with a proof or certificate and its source attached; successful sampling supports a
  measurement.
- **Measure a view.** Take the recipe of a view from the Brotoscope or the player, and measure what it shows.

## What it produces

- **Result data:** plain tables (CSV or JSON). Brotprobe makes no renders; pictures belong to the Brotoscope and
  the player.
- **A recipe with every result (planned contract).** The recipe records everything that produced the number: the
  map and its brackets, the coordinate convention, how the parameter and the section (or seed) are built, the
  iteration budget, the radius threshold, the sample grid and its order, the random seed where one is used, the
  arithmetic and backend, and the exact versions or hashes of the blocks. Running the recipe again is compared
  under a declared tolerance; bit-for-bit equality is claimed only where it has been tested. Opening the matching
  view in the Brotoscope is a planned join: it stays planned until a shared recipe schema and code that reads it
  exist on both sides.

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

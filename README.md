# Strong NP-Completeness of 3-Partition — Formal Proof

A **16-page formal proof**, written in LaTeX, that the **3-Partition** problem is
**strongly NP-complete**, reproducing the full reduction chain from Garey & Johnson's
*Computers and Intractability* (problem [SP15]).

📄 **[Read the proof (PDF)](./3partition-np-complete.pdf)**

## Contents

- Membership: 3-Partition ∈ NP (with an `O(n)` verifier).
- **Reduction chain** `3-Dimensional Matching ≤ₚ 4-Partition ≤ₚ 3-Partition`
  via **pseudo-polynomial transformations** (Garey & Johnson Theorems 4.3 & 4.4).
- Zone-encoding with powers of `r = 32q`; instance-size and bound arguments (mod-`r` analysis).
- A documented **erratum** in the printed bound of Garey & Johnson (`15|A|³` term).
- Applications: multiprocessor scheduling, bin packing, graph bandwidth, Tetris.
- Comparison of the course reduction chain (3-SAT → … → Partition) vs. the Garey–Johnson chain.

## Topics

Complexity theory · strong vs. weak NP-completeness · pseudo-polynomial algorithms ·
polynomial-time reductions · formal proof writing (LaTeX, `amsthm`, `tikz`, `tcolorbox`).

## Build

```bash
pdflatex 3partition-np-complete.tex
```

---
Author: **Ismael Sallami Moreno** · Modelos Avanzados de Computación · University of Granada.

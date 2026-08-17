# 3-Partition-NP-Completeness

A formal proof, written in LaTeX, that 3-Partition is NP-complete in the strong sense.

## Context

Coursework for **Advanced Models of Computation (MAC)**, year 4 of the double degree in
Computer Science and Business Administration, University of Granada (2024-25). Solo
work.

## The problem

The course proves NP-completeness through the usual chain that ends in Partition, which
only gives weak NP-completeness: Partition has a pseudo-polynomial dynamic programming
algorithm, so it is only hard when the numbers are large. The assignment was to prove
the stronger statement for 3-Partition — that it stays intractable even when every
number is bounded by a polynomial in the size of the input — and to do it as a proof
that stands on its own, not as a sketch.

## The solution

The proof follows the chain Garey and Johnson use, not the one from the course:

```
3-Dimensional Matching  ≤p  4-Partition  ≤p  3-Partition
```

Both steps are **pseudo-polynomial transformations**, which is what carries strong
NP-completeness across a reduction; a plain polynomial reduction does not. Each element
of the 3DM instance becomes a number whose digits, in base `r = 32q`, are laid out in
zones that cannot interfere with each other, so a sum can only hit the bound `B` when
the elements it adds up come from one triple. The document proves that the zones do not
carry, that the instance stays polynomial in size, and that the numbers stay bounded.

Membership in NP is the easy half and is proved with an `O(n)` verifier.

Along the way the printed bound in Garey and Johnson does not come out: their `15|A|³`
term is off. The document works out the right one and keeps the discrepancy written
down as an erratum instead of quietly using the corrected value.

## Layout

```
3partition-np-complete.tex   the proof
3partition-np-complete.pdf   the compiled document, 16 pages
```

## Requirements

- TeX Live 2023 or newer, with `amsthm`, `tikz` and `tcolorbox`
- `latexmk`, to resolve the cross-references in one command

## Build and run

```bash
git clone https://github.com/Ismael-Sallami/3-Partition-NP-Completeness.git
cd 3-Partition-NP-Completeness
latexmk -pdf 3partition-np-complete.tex
```

## Results

16 pages: membership in NP, the two reductions with their zone analysis, the erratum,
and a closing section that compares the course chain with the Garey–Johnson one and
says what each is good for. The applications section covers multiprocessor scheduling,
bin packing, graph bandwidth and Tetris, which are the problems whose hardness this
result is normally used to establish.

## What I learned

- **Strong and weak NP-completeness are not a detail of vocabulary.** Partition and
  3-Partition sit on either side of the line, and the practical consequence is whether
  dynamic programming saves you.
- **A reduction that is polynomial is not automatically enough.** Carrying strong
  NP-completeness needs the transformation to be pseudo-polynomial, and that condition
  is easy to skip over when you copy the shape of a proof without its hypotheses.
- **The limitation**: the proof reproduces a known result and adds no new mathematics.
  Its value is that it is complete and checkable, and that the erratum is documented.
  It also stops at 3-Partition: the applications are cited, not proved.

## Author and licence

Ismael Sallami Moreno. Released under the MIT licence (see `LICENSE`).

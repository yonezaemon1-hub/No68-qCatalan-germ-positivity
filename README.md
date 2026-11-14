# Research No.68 — q-Catalan germ positivity through a=32

**Exact Finite Verification of q-Catalan Germ Positivity Through a=32**  
**Ryutaro Yonezu — Independent Researcher**  
**v1.0 — 15 November 2026 — Unreviewed preprint**

**DOI:** [10.5281/zenodo.24223952](https://doi.org/10.5281/zenodo.24223952)  
**Zenodo record:** [Version 1.0](https://zenodo.org/records/24223952)

Exact finite computations verify coefficientwise nonnegativity for all **6,426 admissible q-Catalan germs with 3 ≤ a ≤ 32**, including **4,918 for a=21..32**. No negative coefficients were found. This extends the range explicitly documented in Drew Armstrong's published article (a≤20); it does not establish exclusive historical priority or prove the unrestricted conjecture.

## Status and scope

- Finite computer-assisted verification; no claim for arbitrary a.
- **AI-assisted audit; no independent human peer review.**
- **NOVELTY INCONCLUSIVE; REFERENCES PARTIAL.**
- **Copyright (c) 2026 Ryutaro Yonezu. All rights reserved.**

Public access to the paper and code does not grant redistribution, modification, or software reuse rights. See [LICENSE.txt](LICENSE.txt). No additional execution or reuse license is granted here.

## Publication assets

- [Preprint PDF](No68_v1.0_PREPRINT.pdf)
- [LaTeX source](No68_v1.0_SOURCE.tex)
- [Reproducibility kit](No68_v1.0_REPRODUCIBILITY.zip)
- [SHA-256 checksums](SHA256SUMS.txt)

The reproducibility ZIP contains frozen mathematical source, expected values and result summaries, plus documentation and verification runners. Private audit archives, raw Windows logs, personal machine paths and unrelated research are excluded.

## Reproduction

Extract the reproducibility ZIP and enter its directory. Python 3.10+ and the standard library are sufficient:

```sh
python -B verify_public_data.py
python -B verify_small_cases.py
python -B run_reproduce.py --a 21
python -B run_reproduce.py --a 32
python -B run_reproduce.py --full
```

The first command checks package/data consistency; `--full` recomputes a=21..32. C++17 with Boost.Multiprecision supports two numerator methods:

```sh
g++ -O3 -std=c++17 verify_256.cpp -o verify_256
./verify_256 recurrence 32
./verify_256 inclusion 32
```

The C++ and Python recurrence implementations share the bounded numerator recurrence; C++ inclusion–exclusion is a distinct numerator algorithm. All use the same algebraic quotient identity. `verify_bruteforce_to8.py --a 6` (and 7,8) enumerates the definitions directly and uses ordinary polynomial long division. The full calculation can use substantial memory and time.

## Verification provenance

The frozen manuscript records earlier AI-assisted verification reports and author-operated Windows runs. The November 14 Windows full run was reported as 14 zero exit codes in 6 minutes 20 seconds using Windows 10, PowerShell 5.1 and Python 3.12.10. Its original logfile bytes were not supplied for independent source-log authentication and are not published. Reported Windows execution is distinct from independently rerunning the mathematical programs in the publication environment. No human peer review is claimed.

Publication preparation independently reran Python for all a=21..32, C++ recurrence and inclusion–exclusion for a=3..32, and direct enumeration for a=6,7,8. All freshly executed checks agreed with the frozen results. The eight frozen mathematical/data/license files remain byte-identical to the audited candidate; version labels and publication documentation were edited without changing mathematics.

## Reference

Drew Armstrong, *Lattice Points and Rational q-Catalan Numbers*, Annals of Combinatorics (2026), published April 28, 2026. [DOI: 10.1007/s00026-026-00819-9](https://doi.org/10.1007/s00026-026-00819-9). The fixed numbering is Definition 8.2, Conjecture 8.4 and Conjecture 9.2. [arXiv:2403.06318v4](https://arxiv.org/abs/2403.06318v4), revised April 17, 2026.

The bounded consequences use Armstrong's established implications. Ribbon partitions (Conjecture 10.2) and the unrestricted germ conjecture are not proved by this work.

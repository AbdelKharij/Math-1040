# Finite Mathematics — conversion notes

Source: `MATH_1040.zip`, `FA2025/` only (HW1–HW9, Exams 1–3, Practice Exams 1–3,
Final, Practice Final). Original documents are an instructor's print worksheets.

Every problem with a determinate answer was converted to an interactive Ximera answer
(`\answer`, `\multipleChoice`, `\selectAll`); open-ended "justify"/"sketch" parts use
`\freeResponse` with a worked solution. All numeric answer keys were computed
independently and cross-checked.

## Errors found in the original materials

These are genuine problems in the instructor's sources, not conversion artifacts. The
Ximera answer keys follow the **corrected** values, so the pages diverge from the PDFs
at these points.

1. **HW2, Problem 1(a).** The source carries the answer `{7,9}` in a LaTeX comment, but
   with `U = {1,2,3,4,5,7,9}` and `A = {2,3,4,5}` the complement is
   **`Ā = {1,7,9}`** — the element `1` was omitted. Parts (b) and (c) are unaffected,
   since `1` is not in `C` either way.

2. **Exam 3, Problem 3.** The source does `\includegraphics{FA2025/Exams/E(X)=32dollars.png}`,
   but **no such file exists**. The only matching figure in the zip is
   `E(X)=31.5dollars.png`, whose distribution ($5:0.3, $10:0.1, $20:0.2, $50:0.3,
   $100:0.1) has an expected value of **$31.50**, not $32. The answer key uses $31.50.
   If the intended figure was a different distribution worth $32, this problem needs
   re-checking.

## Judgment calls worth confirming

3. **HW6, Problem 2(b).** The original asks for the answer "to the nearest percent",
   but the true value is 99.79%, which rounds to a rather uninformative 100%. The
   activity asks for two decimal places instead; the solution notes the
   nearest-percent value.

4. **Practice Exam 2, Problem 1(a).** The claim — "the multiplication principle can be
   used to count any situation that can be framed as a series of choices made one at a
   time" — is genuinely ambiguous. It is marked **False**, on the grounds that part (b)
   of the same problem gives the counterexample (choosing a subset of a fixed size is a
   sequence of one-at-a-time choices, but multiplying overcounts). If the intended
   answer was True, parts (a) and (b) contradict each other.

## Deliberate omissions

- Exam front matter (name lines, calculator/phone policy, point totals, "Total Score")
  is print-specific and was dropped.
- The syllabus and course calendar were excluded by request.
- Vertical spacing directives (`[40pt]`, `\vfill`) that reserved room for handwritten
  work have no analogue online and were dropped.
- HW4's commented-out Monty Hall problem was left out, as it is commented out in the
  source.

## Figures

Two exam figures were copied to `xmPictures/` and renamed to LaTeX-safe names:

| original | here |
| --- | --- |
| `P=0.63.png` | `binomialDistributionSeven.png` |
| `E(X)=31.5dollars.png` | `prizeDistribution.png` |

The original filenames encode the instructor's own answers; the images themselves are
legitimate problem data (distributions the student reads values from).

## Build

Verified locally with `lualatex` against the class files in `.ximera_local` — all 17
activities and the `math1040.tex` xourse compile without errors (88pp).

Publishing uses the GitHub Actions workflow in `.github/workflows/serve-ximera.yml`.
Note that `XM_COMPILE_SEQUENCE` is set in `xmScripts/config.txt`, not as a workflow
`env:` — `xmlatex` only forwards six environment variables into the container, so a
workflow-level setting is silently ignored.

# Finite Mathematics — conversion notes

This course covers sets, counting, probability (conditional probability, Bayes' theorem,
binomial distributions, expected value), and game theory. It is institution-neutral and
meant to be usable by any university.

The source was a set of printed worksheets and exams from four semesters. Each semester is
one section (`\part`) of the xourse:

| section | folder | activities |
| --- | --- | --- |
| Spring 2025 | `sp2025/` | 13: HW 1–8, Practice Exams 1–2, Exams 1–2, Final |
| Fall 2025 | `fa2025/` | 17: HW 1–9, Practice Exams 1–3, Exams 1–3, Practice Final, Final |
| Spring 2026 | `sp2026/` | 17: HW 1–9, Practice Exams 1–3, Exams 1–3, Practice Final, Final |
| Fall 2026 | `fa2026/` | 1: HW 1 (the only material yet written for that term) |

Every problem with a definite answer is interactive (`\answer`, `\multipleChoice`,
`\selectAll`). Open-ended "justify" and "sketch" parts use `\freeResponse` with a model
answer. Worked solutions are in `feedback` environments, which stay hidden until the
student checks their work. All numeric answers were computed independently and checked
against the source keys. Where the two disagreed, the corrected value is used and listed
below.

## What was left out

- **Syllabi, calendars, and schedules**, as requested. The same goes for anything that
  identifies an institution, course number, instructor, or local place.
- **Large-print (accommodation) exam copies.** Their questions match the regular exams,
  and one of them names a student.
- **Spring 2026 HW10** is a placeholder note saying the homework was never written. There
  is nothing to convert.
- Print-only front matter (name lines, calculator policy, point totals) and the vertical
  space left for handwritten work.
- A Monty Hall problem that is commented out in one semester's HW4 source. Spring 2025's
  HW4 includes it, so it appears there.

## Errors in the source, and how they were resolved

1. **Fall 2025 HW2, Problem 1(a)**: with $U=\{1,2,3,4,5,7,9\}$ and
   $A=\{2,3,4,5\}$, the complement is $\bar A=\{1,7,9\}$. The source's answer omits $1$.
2. **Fall 2025 Exam 3, Problem 3** includes a figure file that does not exist. The only
   matching figure has expected value \$31.50 (not \$32), and it is used here as
   `prizeDistribution.png`.
3. **Spring 2025 HW6**: among non-voters, the source's percentages (20, 25, 30, 30) sum to
   105%. "Other" is taken to be 25%.
4. **Spring 2026 HW6**: the source defines the false-negative rate as
   $1/\text{sensitivity}$ and the false-positive rate as $1/\text{specificity}$. The
   correct definitions are $1-\text{sensitivity}$ and $1-\text{specificity}$, and the
   answers use them.
5. **Spring 2026 Exam 1, sets problem**: the questions refer to a set $D$ that is never
   defined. The activity supplies $D=\{7,8,9,10\}$.
6. **Spring 2026 Exam 3** includes a screenshot that is not in the source files. The
   matching distribution figure from the same term (`raffleDistribution.png`) is used in
   its place.

## Judgment calls worth confirming

- **HW6, "to the nearest percent"**: the true value, 99.79%, rounds to an uninformative
  100%, so the activity asks for two decimal places.
- **Practice Exam 2, Problem 1(a)**: "the multiplication principle can count any
  situation framed as a series of one-at-a-time choices" is marked **False**, because part
  (b) of the same problem is the counterexample (choosing a subset overcounts).
- **Cross-references between semesters**: a feedback that mentions "Homework N" always
  points to a homework in the same semester. Homework numbering differs between terms, so
  those references were checked individually.

## Figures

In `xmPictures/`: `binomialDistributionSeven.png` and `prizeDistribution.png` (Fall 2025),
and `binomialDistributionSix.png` and `raffleDistribution.png` (Spring 2026). They were
renamed because the original filenames contained the answers.

## Build

Every activity compiles with `lualatex` against the class files. `xmPreamble.tex` is loaded
automatically by `ximera.cls`, so activities must not `\input` it. Publishing uses the
GitHub Actions workflow in `.github/workflows/serve-ximera.yml`. `XM_COMPILE_SEQUENCE`
belongs in `xmScripts/config.txt`, because a workflow-level `env:` is silently ignored.

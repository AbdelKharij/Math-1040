# Finite Mathematics

An interactive online version of this course, built with
[Ximera](https://ximera.osu.edu/). Students read the page, type answers into the
problems, and get immediate feedback with a full worked solution.

**Live site:** <https://xerxes.ximera.org/abdelkharij-math-1040/finiteMathematics>

Topics: sets and counting, probability, conditional probability and Bayes' theorem,
binomial distributions, expected value, and game theory.

## What is in it

Each semester is its own section of the course:

| section | folder | activities |
| --- | --- | --- |
| Spring 2025 | `sp2025/` | 13 |
| Fall 2025 | `fa2025/` | 17 |
| Spring 2026 | `sp2026/` | 17 |
| Fall 2026 | `fa2026/` | 1 |

48 activities in all, holding 205 problems: 756 answer blanks, 149 multiple-choice and
6 select-all questions, 19 open-ended questions, 503 worked solutions, and 191 hints.

Students can work any section; nothing is hidden or locked. A worked solution stays
hidden until the student clicks **Check work**.

## Using it with a class

Send students the live link above. There is no enrollment, login, or grade book —
Ximera records progress in the student's own browser, so this works as practice and
review material rather than as something to collect.

**The real exams are included and are publicly visible.** That was a deliberate choice.
If you ever want a problem taken off the public site, delete or comment out its
`\activity{...}` line in `finiteMathematics.tex` and push.

## Editing

- One activity = one `.tex` file. Edit it like any LaTeX document.
- `finiteMathematics.tex` is the table of contents. `\part{...}` starts a section and
  `\activity{folder/file.tex}` adds an activity in order.
- To add a semester, make a folder, put the `.tex` files in it, and add a new `\part`
  with its `\activity` lines.
- Add shared macros to `xmPreamble.tex`, not to individual activities. Activities must
  **not** `\input` the preamble; Ximera loads it automatically.
- Pictures live in `xmPictures/` and are referenced by filename alone.

Every push to `main` rebuilds and republishes the site automatically (a few minutes).
You can watch it under the repository's **Actions** tab. If a publish ever fails at the
last step with a `502` from the server, just re-run the failed job.

## Notes on the conversion

`COURSE-NOTES.md` records everything worth knowing: which source material was left out
and why, about a dozen errors found in the original worksheets and answer keys (the
online version uses the corrected values), and a few judgment calls that are worth your
review.

The course is written to be institution-neutral, so it carries no university name,
course number, instructor name, or local references, and can be used by anyone.

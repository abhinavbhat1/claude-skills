---
name: "course-command-centre"
description: "Build an exam-prep command center and an intuition lab for any course from its notes, lectures and past exams: from-zero lessons, glance cards, plan, mocks, tutor, with a strict vetting pass."
---

# Course command centre

Build two published pages for one course and one exam:

1. **The command center**: the complete, exam-aligned study guide. Every topic, every formula, a dated plan, drills, mocks, progress tracking, and a built-in tutor.
2. **The intuition lab**: a second, lighter page that teaches the intuition behind the math with interactive instruments, matched to the format of the real exam.

Build the command center first. Build the lab only when asked or when the student says they are brute-forcing derivations without understanding.

## 0. Inputs to collect before writing anything

Ask only for what is missing. Read everything that exists.

- Syllabus: exam date, time, room, length, coverage (cumulative or not), grading rule (for example best two of three).
- The instructor's notes or textbook sections, lecture slides or board photos, with lecture dates.
- Any past exam or the student's own marked or unmarked exam script. This is the single most valuable input: it fixes the question style and gives the student's personal error list.
- Class statistics for past exams if available.
- The student's status: what is done, what is not started, hours available per day, fixed commitments (check the calendar if connected).
- The course folder on the student's computer, if linked.

Record the instructor's own notation and conventions module by module. Where the note, the board and the exam disagree (a sign, a letter, a dial that multiplies in one place and divides in another), write the disagreement down. These become traps.

## 1. Writing rules (non-negotiable)

- Teach from zero. Never open with a dense definition.
- Every term and every symbol gets a full plain sentence at first use. No compressed definitions in brackets or after semicolons.
- Every claim is derived or shown with small numbers. Never state a formula bare.
- In every worked step: formula, then the values substituted into it, then the result. Nothing assumed. No quantity used before it is given or computed.
- Use the instructor's notation, and use the same symbols in summaries as in the full lesson of that module. When the exam used different letters, say so in words ("Exam 1 wrote E_k for a_k").
- No em-dashes. No double negatives. One spelling convention throughout. Direct, unpadded prose.
- Numbers chosen so that the arithmetic is clean, in the style of the real exam (for example energies 0, log 3, log 9 so that exponentials cancel).

## 2. Command center: feature list

### Structure
- Split the course into modules of 3 to 5 ideas each, in the order the student should study them (which can differ from lecture order; say why when it does).
- A module 0 for prerequisite math from zero, if the student needs it.
- Left rail with all modules, each showing its planned date and four progress dots. A module picker on phones. Hash routing so links go to a module or an idea.

### Inside every module
- **Source line**: note section, equation range, lecture date.
- **Quick glance card** at the top (collapsible, one setting for all modules), with:
  - The idea, one paragraph in plain words.
  - Coming from earlier modules (titles of the bridges, when the module is studied after related material).
  - Read the formula: the one or two key formulas, an "in words" sentence, and a piece-by-piece table of what each part does.
  - Watch the formula move, with numbers: numbered steps, each with its reason; reuse a real past exam question and finish it where one exists.
  - Every idea and every formula in this module: one block per idea with a one-sentence takeaway, every display formula of the lesson pulled in automatically with a plain-words reading, plus extra formulas that the lesson only has in running text (special cases, limits, derivation steps, counts).
  - Why it works: the two or three "why" questions a grader would ask.
  - Traps, edge cases, tricky cases: including the student's own past exam mistakes, named.
  - Try it, exam style: one or two numericals with click-to-reveal worked answers as numbered steps.
- **Where this fits**: a short story placing the module in the course.
- **Per idea, a fixed ladder**:
  - (optional) Coming from Part X: a bridge from material the student has already studied, with the formulas side by side and a small number check.
  - Level 1, everyday picture, no jargon.
  - Level 2, course level, in the instructor's words and notation.
  - Level 3, exam level: traps, common wrong answers, edge cases, misprints in the note, plus a "Big picture" box linking the idea to other modules.
  - Level 4, full working: every line of the derivation and worked-numbers boxes to cover and redo.
  - Three questions to answer before the next idea.
- **End of module**: drills (about seven), word list, summary.

### Course-wide pages
- **Plan**: a dated, hour-by-hour plan to the exam, built from the student's real availability, with a per-module method, hours per day, and "if you slip" rules. Rebuild it whenever the status changes, and mark older plans as superseded.
- **Daily quizzes** and **timed mock exams** in the real exam's format and length.
- **Corrections**: the student's past exam, question by question, with what they wrote, the right answer and the reason.
- **Formula sheet** and **crash cards** for last-day review.
- **Videos or resources**: a short ordered watch path, built only from links that were actually opened and checked.

### Progress
- Four dots per module (read, drills done, next-day review, exam retest), stored in the browser.
- The four mastery buttons (1 Read, 2 Drills done, 3 Next-day review, 4 Exam retest) appear twice in every module: directly under the module title at the top, and again in the navigation bar at the bottom. Both rows read and write the same stored state, so ticking one updates the other, the rail dots and the header strip at once. Test this: click a top button, confirm the bottom row, the dots and the stored value all change, at phone and desktop width.
- A header strip: time to the exam, percent done, and whether the student is ahead of or behind the plan's daily targets.

### Built-in tutor ("Ask")
- A drawer using the page's ask-Claude capability. One conversation for the whole guide, kept across modules and reloads, with a "New chat" button.
- Every request is rebuilt fresh so context never falls out: a brief with answer rules, the course conventions, the student's past exam mistakes, a build-time digest of every module (generated from the glance cards), the recent turns, then the full text of the idea on screen, up to three matching ideas from other modules found by an in-page keyword search, any selected passage, and the progress ticks.
- Do the cross-module lookup in the page, not with model tool calls, so each answer is one request and arrives in seconds.
- Answer rules in the brief: answer in the first sentence; match length to the question; never state a formula bare; define symbols; use the guide's notation; say plainly when the student is wrong and recompute their arithmetic; name the module and idea relied on; quiz only when asked, one question in the real exam's style.
- Fast mode by default and a deeper mode for hard derivations. Streaming Markdown with math. Stop button. Retry on failure.
- Select any text on the page to get an "Ask about this" button. Keyboard shortcut to open and close. Under each answer: copy, shorter, step by step, with numbers, quiz me, and a "looked at" line listing what was sent.

### Reading comfort
- Math rendered with MathJax, with a copy handler so selections copy as LaTeX, a click selects one formula, and selected formulas highlight.
- Light and dark themes, phone and desktop layouts, long formulas scroll inside their own box, print styles.

## 3. Intuition lab: feature list

- One page per topic (about 15 to 20), each with: a plain picture, one interactive instrument (sliders or draggable points drawing live on a canvas or SVG), a "Try" list of specific settings to set and what to notice, the formula read in words, and two or three questions with instant marking or reveal-and-self-mark.
- Instruments are small specs mounted by one helper. Typical ones: an energy landscape, a softmax with a temperature dial, a backprop graph with live numbers, a step-size plot, a bound that moves with sample size, a bias-variance dartboard, a posterior update, a mixture fit, a sampler.
- Every "Try" line must be checked against the instrument's real range and defaults.
- Extra pages: a map of the course, a rehearsal exam in the real format worth the real number of points, the past exam corrected, and "formulas in words".
- A readiness meter from the answered questions, stored in the browser, and the same tutor drawer with the current page's text.

## 4. Build method

Keep content as plain text files and generate the page with a build script, so content can be reviewed and fixed without touching HTML.

- `lad/<module>.txt`: `FITS:` paragraph, then per idea `== title`, `L1:`, `L2:`, `L3:` (bullets), and exactly three `Q:` / `A:` pairs. Display math in `\[ \]`.
- `links.txt` and `bridge.txt`: keyed `@ module.ideaIndex`, one paragraph or bullet per line (Big picture links; Coming-from bridges).
- `glance.txt`: `@ id | title`, `IDEA:`, `MOVE: subtitle` with lines `LaTeX || reason`, `WHY:` bullets, `TRAPS:` bullets, `Q:` / `A:` where answer steps are separated by ` ;; `.
- `readf.txt`: per module `F:` formula, `SAY:` in words, `- piece || meaning`.
- `all.txt`: per module and idea, `S:` takeaway, `Fk:` a reading of the k-th display formula of that idea in the lesson file (the formula itself is pulled from the lesson so it cannot drift), `X: formula || reading` for extras. The build asserts that every idea is present and every display formula has a reading.
- `plan.html`, `days.json` (date label per module), quiz files, and small CSS and JS add-on files.
- The build asserts: counts of cards and ideas, no em-dashes, every anchor it patches exists exactly once.
- Generate the tutor's all-module digest from the glance files at build time and embed it as JSON.

Publish as an artifact page with the ask-Claude capability declared. Republish to the same link on every change.

## 5. Vetting before every hand-back (do all of these)

1. **Recompute every number in code.** Never trust mental arithmetic, including your own worked answers.
2. **Independent reviewers.** Send each batch of new content to a fresh reviewer that has not seen it being written. Give it one job at a time and tell it the intentional conventions so it does not flag them:
   - numbers: recompute all by script;
   - correctness: every conceptual claim, overclaims, internal contradictions;
   - nothing assumed: every step shows its substitution;
   - notation: each summary uses the same symbols as its lesson file;
   - completeness: read each lesson in full and list exam-relevant items missing from the summary;
   - cross-references: every claim about another module checked against that module's file;
   - style: em-dashes, double negatives, spelling.
   Ask for a numbered list with quoted text and paste-ready corrections. Apply the findings, and send reviewer-written additions to a second reviewer.
3. **Check statements about the source.** Verify claims about the instructor's note, lectures and the student's exam against the files. Where they cannot be verified, say so or soften the claim. Do not guess what an exam option said.
4. **Render gate.** Open every section in a headless browser at phone width (dark) and desktop width (light): no horizontal overflow, no unrendered math, no script errors.
5. **Functional test** with a fake tutor runtime: context sent, cross-module lookup, history, selection, glance cards present and typeset, copy gives LaTeX.
6. **Live test** of the tutor in the student's real browser when one is connected: one cross-module question, one follow-up, one deliberately wrong claim.
7. **Report honestly**: what was checked, what was found and fixed, and what was not checked (for example fixes not re-reviewed, a mode not tested live, a real phone not tried).

## 6. Working with the student

- When the student gives their status, rebuild the plan and, if a calendar is connected and they ask, retime the existing study blocks to match. Do not create or delete other events. Flag conflicts such as another deadline on the same night.
- Use the past exam as the reference for style, for traps, and for one or two numericals per module.
- When the student says the tutor or a summary is poor, treat it as a design problem: find what context was missing or what format was forced, and rebuild it.
- When asked whether a target score is realistic, answer plainly from the evidence: class statistics, hours left, the kind of errors made before, and the result of a timed mock.
- Keep a short project note of decisions, versions, conventions and what was vetted, so a later session can continue.
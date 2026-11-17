# Skills

Agent skills I wrote for my coursework and side projects. One folder per skill. Each folder has a `SKILL.md`: a short frontmatter header with the name and description, then the instructions the agent follows.

## Skills in this repo

| Skill | What it does |
|---|---|
| [course-command-centre](course-command-centre/SKILL.md) | Turns a course's notes, lectures and past exams into an exam-prep study guide, plus an optional intuition lab. |

## course-command-centre

I built this one for exam season. You give it one course and one exam. It reads the syllabus, the instructor's notes, the lecture slides and any past exam you have, then builds a study guide as a web page.

The guide splits the course into modules of three to five ideas and teaches each from zero, with real numbers worked through every step. Each idea climbs four levels: an everyday picture, the course version in the instructor's notation, the exam version with the traps, and the full derivation. Around that you get a dated study plan built from the hours you actually have, timed mock exams in the real format that you answer in the page and get graded on, a question-by-question correction of your last exam, and a formula sheet for the night before. There's a tutor built into the page too. It sees the module you're on and pulls in related ideas from other modules when you ask it something.

The second page, the intuition lab, is optional. Each topic gets a small interactive instrument, sliders driving a live plot, with settings to try and a few questions. It only gets built if you ask.

The part I care most about is the vetting. Before anything comes back, every number is recomputed in code, separate reviewers check the math, the notation and what's missing, and every page is rendered at phone and desktop width. A study guide with wrong arithmetic is worse than having none.

## Using a skill

Copy the skill's folder into your agent's skills directory, or upload its `SKILL.md` as a custom skill. Then ask for it by name, for example:

> Use course-command-centre to build a study guide for my operating systems midterm.

## Layout

```
course-command-centre/
  SKILL.md
```

Each new skill gets its own folder at the top level.

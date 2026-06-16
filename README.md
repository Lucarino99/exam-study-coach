# Exam Study Coach

**Your own personal actuarial/finance exam coach, run by Claude Code.** Use this
template to spin up a private study coach for *your* exam. On a schedule it asks
**one** exam-realistic conceptual question, **pings your phone**, grades your reply
like a real exam grader, and remembers everything in your repo so it gets smarter
about *your* weak spots over time.

> This is an **exam helper per person — not a shared content hub.** Each person who
> uses this template gets their **own** private copy. Nothing is shared between
> users. You bring your own exam and (optionally) your own materials.

Built for **actuarial/finance professional exams** — SOA, CAS, CFA, FRM — where the
model's knowledge is strongest. Other subjects work too (it's exam-agnostic), just
with less depth.

---

## What you get

- A scheduled [Claude Code **routine**](https://claude.ai/code) that drills you
  automatically — no app to open, no flashcards to flip.
- **Phone notifications** for every question (this is required — see below).
- An **exam grader** that awards point-based partial credit, cites your materials
  when you add them, and tracks your progress in `state/`.
- A **conversational first-run wizard** — no YAML to hand-edit. On the first run it
  interviews you (exam, date, timezone, cadence, style) and configures itself.

## ⚠️ Prerequisites — read honestly before you start

You need **all** of these. If any is missing, the coach cannot run:

1. **A Claude paid subscription** — **Pro, Max, or Team** — with **Claude Code on
   the web** and **Routines** (currently a **research preview**) enabled on your
   account.
2. **GitHub connected** to Claude (the Claude GitHub App authorized on your copy of
   this repo) so the routine can read/write your repo.
3. **The Claude mobile app installed, signed in, with notifications turned ON.**
   The coach pings your phone for every drill. **No phone notifications = the coach
   is useless to you.** Onboarding is not considered complete until a **test
   notification is confirmed received on your phone.**

## "Use this template"

1. Click **“Use this template” → “Create a new repository”** at the top of this
   repo. Name it whatever you like (e.g. `my-cfa-coach`).
2. **If you plan to add copyrighted prep materials, make your new repo PRIVATE**
   (see Copyright below).
3. Follow **[SETUP.md](SETUP.md)** — it walks you through connecting GitHub,
   creating the routine, running the first-run wizard, confirming the phone ping,
   and setting your schedule.

That's it — the wizard handles configuration for you.

## The phone-ping requirement

This coach is built around being **interrupted on your phone** to answer a quick
question, the way a tutor would text you. Every drill posts the question and then
sends a short push notification to your phone via the Claude mobile app. During
first-run setup the wizard sends a **test notification and will not finish until
you confirm you received it.** If you won't enable mobile notifications, this
template isn't for you.

## ⚠️ Copyright warning

**This template ships with ZERO exam content.** Do not change that on a public repo.

- **Never upload paid prep materials** (TIA, ACTEX, ASM, official past-exam PDFs,
  copyrighted notes, etc.) **to a PUBLIC repository.** That infringes copyright.
- If you want the coach to grade against your purchased materials, **keep your copy
  of this repo PRIVATE** and drop them in `materials/` (which is git-ignored except
  for its README). See [`materials/README.md`](materials/README.md).
- Materials you add are yours and your responsibility; the framework's
  [MIT license](LICENSE) covers the framework **only**, not exam content.

## Privacy

Each person's copy is **their own private repository**. There is no shared backend,
no central database, and **no data is shared between users**. Your config, your
materials, and your performance history live only in your repo. See
[SECURITY.md](SECURITY.md).

## Disclaimer

This is an **unofficial study aid**, not affiliated with or endorsed by the SOA,
CAS, CFA Institute, GARP, or any exam body. **Grading is approximate** — it is an
AI grader's best effort against a model solution, not an official mark. Always
verify against your authoritative source materials. Use it to practice, not as a
source of truth.

---

### How it's built

- **[`ROUTINE_PROMPT.md`](ROUTINE_PROMPT.md)** — the exam-agnostic coach engine you
  paste into the routine. Drives both the first-run wizard and the ask/grade loop.
- **[`config.example.yml`](config.example.yml)** — the documented config schema
  (the wizard writes your real `config.yml` for you).
- **[`grading/RUBRIC.md`](grading/RUBRIC.md)** — point-based partial-credit rubric.
- **`syllabus/`** — your topic map (the wizard derives it).
- **`materials/`** — your private sources (git-ignored on public repos).
- **`state/`** — `history.md`, `coverage.md`, `profile.md`: the coach's memory.

See **[SETUP.md](SETUP.md)** to get going.

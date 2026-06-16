# Setup

This gets your personal exam coach running end to end. Budget ~15 minutes. You'll
finish with a scheduled routine that drills you and pings your phone.

> **Prerequisites** (all required — see the [README](README.md#️-prerequisites--read-honestly-before-you-start)):
> a Claude **Pro/Max/Team** subscription with **Claude Code on the web** and
> **Routines (research preview)** enabled; **GitHub connected** to Claude; the
> **Claude mobile app** installed with **notifications ON**.

---

## 1. Create your copy from this template

1. Click **“Use this template” → “Create a new repository.”**
2. Name it (e.g. `my-frm-coach`).
3. **Visibility:** if you intend to add **copyrighted prep materials** (TIA, ACTEX,
   ASM, official past-exam PDFs, etc.), choose **Private**. If you'll rely only on
   the model's general knowledge, public is fine. You can change this later under
   **Settings → General → Change repository visibility**.

   > ⚠️ Never put paid/copyrighted materials in a **public** repo. See
   > [`materials/README.md`](materials/README.md).

## 2. Connect the Claude GitHub App

So the routine can read your repo and push state back to `main`:

1. Go to **[claude.ai/code](https://claude.ai/code)**.
2. Connect GitHub if you haven't, and **authorize the Claude GitHub App on your new
   repository** (you can grant it to just this repo).

## 3. Create the routine

In **[claude.ai/code](https://claude.ai/code)** → **Routines** → **New routine**:

1. **Prompt:** open [`ROUTINE_PROMPT.md`](ROUTINE_PROMPT.md) in your repo, copy its
   **entire** contents, and paste them in as the routine's instructions.
2. **Repository:** select **your** copy of this repo.
3. **Model:** **Opus**.
4. **Enable “Allow unrestricted branch pushes.”** The coach commits state to `main`
   on every run; without this it can't save your progress.
5. Save the routine. **Leave the schedule for now** — the wizard will tell you
   exactly what to set in step 6.

## 4. Run the first-run wizard

1. Click **“Run now”** on the routine.
2. Because your repo has **no `config.yml` yet**, this first run launches the
   **conversational wizard** instead of asking an exam question. It will ask:
   - which exam, your exam date, your timezone;
   - your daily window + how often you want drills;
   - question style (qualitative / quantitative / mixed) and difficulty.
3. **Confirm** your answers when it summarizes them.

## 5. (Optional) Add your materials

When the wizard asks, **upload your syllabus / notes / past papers + official
solutions into `materials/`** and tell it you're done. The coach will derive a
topic map from them and **prefer them as ground truth** when grading.

- Skip this and it builds a topic map from its own knowledge of your exam (marked
  unofficial until you add materials).
- **Only add copyrighted materials if your repo is PRIVATE.**

## 6. ✅ The notification gate — confirm the phone ping

This is **required**. The wizard sends a **test notification to your phone** and
**will not declare setup complete until you confirm you received it.**

- **Got it on your phone?** Tell the wizard. Setup proceeds.
- **Didn't get it?** Fix and retry:
  - Install/sign in to the **Claude mobile app**.
  - Enable notifications: **Claude app → Settings → Notifications ON**, and allow
    notifications for Claude in your **phone's OS settings**.
  - Enable **Remote Control / notifications for Claude Code sessions** in the app so
    routine runs can reach you.
  - Then have the wizard **resend the test** and confirm.

## 7. Set the schedule the wizard gives you

You can't edit a routine's own schedule from inside it, so the wizard prints the
**exact cron** to paste into the routine UI. For ~90-minute spacing within your
daily window (example, starting 10:00 in your timezone) it gives two triggers:

```
0 10,13,16,19 * * *
30 11,14,17,20 * * *
```

Add these under the routine's **Schedule** (in **your** timezone), confirm **“Allow
unrestricted branch pushes”** is still on, and save.

---

## You're done

From now on, every scheduled run:

1. Picks one under-drilled topic, writes one exam-realistic question, posts it, and
   **pings your phone**.
2. When you reply, grades it (`Score: X/10`, a ✓/~/✗ breakdown, a model answer, and
   a study tip) and updates `state/` on `main`.

Reply to the notification whenever you can — unanswered questions are marked and the
coach moves on, so you never lose your place.

### Troubleshooting

- **No phone ping:** redo step 6 — it's almost always app/OS notification settings.
- **State not saving:** confirm **“Allow unrestricted branch pushes”** is enabled
  and the Claude GitHub App is authorized on your repo.
- **It launched the wizard again:** that means `config.yml` wasn't committed to
  `main`. Re-run; the wizard writes and pushes it.

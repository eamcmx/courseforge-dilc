# Wizard — Quick Start (DILC)

Turn source material (a PDF, slide deck, Word doc, notes, or a YouTube lecture)
into a **single self-contained interactive HTML lecture** — live widgets, maths,
worked examples, and an embedded study buddy — saved straight to your computer.

---

## 1. One-time setup (required)

The Wizard writes the lectures by driving **Claude Code** on your machine. This is
the only hard requirement — without it, generation will not run.

1. **Install Claude Code** — https://docs.anthropic.com/en/docs/claude-code/overview
2. **Sign in once:** open a terminal (PowerShell), run `claude`, and complete the
   login (`/login` if it doesn't prompt). You need a Claude subscription.
   - Quick check: `claude -p "say OK"` should print `OK`.
3. **Install the Wizard:** run `Wizard-refactored-MCP Setup 0.4.5.exe` and launch it
   from the Start menu.

On launch the Wizard checks for Claude. **GitHub and Git are *optional*** — you only
need them if you later want to publish a lecture online. For saving to your hard
drive, ignore them.

> Internet is used **only during generation** (the Claude calls + fetching any
> illustrative images). The finished `index.html` opens **offline**. The optional
> in-page study buddy needs the student's own free Mistral key + internet.

---

## 2. Build a lecture (saving to your computer)

1. **Add your material** — drag a PDF/DOCX/PPTX/TXT/MD/HTML onto the dropzone (or
   paste a YouTube URL). Slides are the primary structure; notes add depth.
2. **One session, or several?** *(optional but recommended)* — click **🔍 Plan
   sessions**. The Wizard reads your material and suggests whether it's one lecture
   or should be split into several, with a breakdown of each. You decide:
   - **Build this session →** builds just that one in depth, or
   - ignore it and build everything as one lecture.
3. **Save to your computer** — under *Where it goes*, click **Browse…** and pick a
   folder on your hard drive. (GitHub stays collapsed — leave it alone.)
4. Click **Extract outline →**, review/tweak the outline, design the widgets, then
   **Generate**.
5. The finished standalone file is written to
   **`<your folder>/<lecture-slug>/index.html`** and is also downloadable from the
   result screen. Double-click it to open in any browser — no server needed.

---

## 3. Good to know

- **Electronics / digital logic** topics get **real interactive logic circuits**
  automatically (gates, adders, live truth tables) — no setup needed.
- **Page design** — leave on *Free-form* (Claude designs it) or pin one of the six
  looks (field manual, blueprint, etc.).
- **Model** — *Opus 4.8* (default, best) or *Sonnet* (faster, higher quota) if you
  are low on Opus usage.
- **The study buddy** baked into each page asks the student for *their own* free
  Mistral API key (kept in their browser). It never uses a shared key.
- **Library** — every lecture is also kept inside the app so you can reopen, edit,
  and re-generate it later.

---

## 4. If something goes wrong

| Symptom | Fix |
|---|---|
| "claude exited 1 / 401" on generate | Your Claude login expired — run `claude` → `/login` again, then retry. |
| "Extract outline" button stays greyed out | Add a source **and** pick a *Save to your computer* folder (or a GitHub repo). |
| Generation is slow | Normal — a full lecture is several Claude calls. The status panel shows live progress. |
| The launch screen nags about GitHub/Git | They're optional; click *Dismiss*. Only Claude is required. |

---
*Wizard-refactored-MCP · TSI — Transporta un Sakaru Institūts*

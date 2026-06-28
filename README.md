# TSI DILC — course-building tools

Two desktop tools for the TSI **DILC** team. Both run on **your own Claude account** (the `claude`
CLI — no API key) and write everything to a folder on your computer. Pick by what you need:

| Tool | What it produces | Where |
|---|---|---|
| **CourseForge** | A whole **course** from a syllabus — per session: interactive lecture + teacher deck + gated worked solutions + hidden instructor key + 80%-gating quiz — ready to mount on Moodle. | [Releases ›](../../releases) → *CourseForge DILC* |
| **Lecture Wizard** | A single **interactive lecture page** from one source (PDF / slides / notes / YouTube) — live widgets, maths, a study buddy — saved as one standalone HTML. Its output can feed CourseForge. | [Releases ›](../../releases) → *Lecture Wizard* |

> One requirement for **both**: **Claude Code (the `claude` CLI) installed and signed in** on each machine.
> First time on a computer? Follow **[claude-setup.md](claude-setup.md)** (≈5 min).

---

# 1 · CourseForge — DILC Edition

Turn a teacher's **syllabus + materials** into a complete **gold-standard, AI-augmented course set** —
an interactive lecture, a teacher deck, gated worked solutions, a hidden instructor key and an
80%-gating formative quiz **per session** — then mount the files on Moodle by hand. It runs on **your own
Claude Pro Max account** (no API key) and writes everything to a folder for you to upload.

> Built for the TSI **DILC** team to reproduce the MSESR gold-lecture pipeline without doing it all by hand.

### ⬇️ Download

From the **[Releases page](../../releases)**, open the **CourseForge DILC** release:

| File | Use it if… |
|---|---|
| **CourseForge-DILC-Setup-…-x64.exe** | You want a normal install (Start-menu shortcut, choose the folder). **Recommended.** |
| **CourseForge-DILC-Portable-…-x64.exe** | You just want to run it with no install. |

Windows 10/11, 64-bit.

### ✅ One-time setup on each machine

**Just one thing:** the **Claude CLI + your Claude account.** Install the `claude` CLI, then in the app click
**Connect Claude** and complete the one-time *"Log in with your Claude account"* step (your **Claude Pro Max**
account — no API key). That's it.

*(Python is bundled inside the app — nothing to install for reading PDFs/Word/PowerPoint or the quality checks.
Use **Settings → Check tools** to confirm Claude is connected.)*

### 🚀 How to use it

1. **Connect Claude** (first run).
2. **＋ New course** → paste/load the **syllabus**, set programme / level / ECTS / language and the **study form**
   (full-time / part-time / distance — this sets how the contact-hours become 2-hour sessions).
3. **Review the plan** — it mirrors the syllabus (one session per topic, expanded by contact hours), then **Approve**.
4. For each session, either drop the teacher's **materials**, *or* attach a ready-made **lecture HTML** (e.g. from
   the Lecture Wizard below) — then **Generate**. You'll see live progress (current step, what the agent is doing, elapsed time).
5. **Export & MOUNTING.md** — open the output folder and follow the generated sheet to mount the five parts on
   Moodle (which file is which resource, plus the 80% quiz-gate + reveal-on-pass settings).

Generation runs **one session at a time** on your Claude account and typically takes ~10–30 min per session.
CourseForge **enriches the teacher's own material** — it does not invent generic content — and won't mark a
session done until it passes the quality gates (richness, interactive widgets, balanced quiz).

### ❓ Troubleshooting

- **"Claude: not connected"** → open a terminal, run `claude`, finish the login, then click **Re-check**.
- **"Python/extraction libs missing"** → install Python 3 and run the `pip install …` line above.
- **A session won't finish** → it re-authors on a failed gate; check the live activity feed. You can re-run it.

---

# 2 · Lecture Wizard

Turn **one source** — a PDF, slide deck, Word doc, notes, or a YouTube lecture — into a **single
self-contained interactive HTML lecture**: live widgets, maths, worked examples and an embedded study
buddy, saved straight to your computer. Great on its own, and its lecture HTML can be attached to a
CourseForge session.

### ⬇️ Download

From the **[Releases page](../../releases)**, open the **Lecture Wizard** release:

| File | Use it if… |
|---|---|
| **Wizard-refactored-MCP-Setup-…-x64.exe** | Normal install (Start-menu shortcut). Grab the latest version. |

Windows 10/11, 64-bit. Unsigned → at the SmartScreen prompt click **More info → Run anyway**.

### ✅ One-time setup

Only one thing is required: **Claude Code installed and signed in**.

1. Install the `claude` CLI — https://docs.anthropic.com/en/docs/claude-code/overview
2. Open a terminal, run `claude`, and complete the login (your Claude account — no API key).
   Quick check: `claude -p "say OK"` should print `OK`.

GitHub is **not** needed — the Wizard saves to your hard drive.

### 🚀 How to use it

1. **Add your material** — drop a PDF/DOCX/PPTX/TXT/MD/HTML onto the dropzone, or paste a YouTube URL.
2. **🔍 Plan sessions** *(optional)* — it analyses the material and suggests whether it's one lecture or
   should be split into several (with a breakdown of each), and **you** decide.
3. **Save to your computer** — under *Where it goes*, click **Browse…** and pick a folder. (GitHub stays
   collapsed and optional.)
4. **Extract outline → review → Generate.** The finished standalone `index.html` lands in your folder
   (`<folder>/<lecture>/index.html`) and is also downloadable from the result screen. Open it in any
   browser — no server needed.

Electronics / digital-logic topics automatically get real interactive **logic circuits** (gates, adders,
live truth tables). Full guide: **[wizard-quickstart.md](wizard-quickstart.md)**.

---

*Internal TSI / DILC tools. Installers bundle the generation engine (and a gold reference lecture used only
as the quality bar). Each runs on your own Claude account; nothing is sent to a third-party API key.*

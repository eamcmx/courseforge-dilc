# CourseForge — DILC Edition

Turn a teacher's **syllabus + materials** into a complete **gold-standard, AI-augmented course set** —
an interactive lecture, a teacher deck, gated worked solutions, a hidden instructor key and an
80%-gating formative quiz **per session** — then mount the files on Moodle by hand. It runs on **your own
Claude Pro Max account** (no API key) and writes everything to a folder for you to upload.

> Built for the TSI **DILC** team to reproduce the MSESR gold-lecture pipeline without doing it all by hand.

## ⬇️ Download

Get the latest installer from the **[Releases page](../../releases/latest)**:

| File | Use it if… |
|---|---|
| **CourseForge-DILC-Setup-…-x64.exe** | You want a normal install (Start-menu shortcut, choose the folder). **Recommended.** |
| **CourseForge-DILC-Portable-…-x64.exe** | You just want to run it with no install. |

Windows 10/11, 64-bit.

## ✅ One-time setup on each machine

The app checks both of these under **Settings → Check tools** and tells you if anything's missing.

1. **Claude CLI + your Claude account.** Install the `claude` CLI, then in the app click **Connect Claude**
   and complete the one-time *"Log in with your Claude account"* step (your **Claude Pro Max** account — no API key).
2. **Python 3** with three libraries (for reading PDFs/Word/PowerPoint and the quality checks):
   ```
   pip install pymupdf python-docx python-pptx
   ```

## 🚀 How to use it

1. **Connect Claude** (first run).
2. **＋ New course** → paste/load the **syllabus**, set programme / level / ECTS / language and the **study form**
   (full-time / part-time / distance — this sets how the contact-hours become 2-hour sessions).
3. **Review the plan** — it mirrors the syllabus (one session per topic, expanded by contact hours), then **Approve**.
4. For each session, either drop the teacher's **materials**, *or* attach a ready-made **lecture HTML** (e.g. from
   the wizard) — then **Generate**. You'll see live progress (current step, what the agent is doing, elapsed time).
5. **Export & MOUNTING.md** — open the output folder and follow the generated sheet to mount the five parts on
   Moodle (which file is which resource, plus the 80% quiz-gate + reveal-on-pass settings).

Generation runs **one session at a time** on your Claude account and typically takes ~10–30 min per session.
CourseForge **enriches the teacher's own material** — it does not invent generic content — and won't mark a
session done until it passes the quality gates (richness, interactive widgets, balanced quiz).

## ❓ Troubleshooting

- **"Claude: not connected"** → open a terminal, run `claude`, finish the login, then click **Re-check**.
- **"Python/extraction libs missing"** → install Python 3 and run the `pip install …` line above.
- **A session won't finish** → it re-authors on a failed gate; check the live activity feed. You can re-run it.

---

*Internal TSI / DILC tool. The installer bundles the generation engine and a gold reference lecture used only as
the quality bar.*

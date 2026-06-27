# Setting up Claude Code (required for both tools)

Both **CourseForge** and the **Lecture Wizard** generate content by driving **your own
Claude account** through the `claude` command-line tool — no API key, nothing shared. You
install it once per machine and sign in with your own Claude (Pro or Max) subscription.

> This is the **only** hard requirement. (CourseForge additionally needs Python — see its
> section in the [README](README.md); the Wizard needs nothing else.)

## 1. Install Node.js

Claude Code runs on Node. If you don't already have it:

- Download the **LTS** installer from **https://nodejs.org** and run it (accept the defaults).
- Check it worked — open **PowerShell** and run:
  ```
  node --version
  ```
  Any **v18 or newer** is fine.

## 2. Install Claude Code

In **PowerShell**:
```
npm install -g @anthropic-ai/claude-code
```

## 3. Start Claude and sign in (with YOUR account)

In a terminal, run:
```
claude
```
- The first time, it walks you through login → choose **"Log in with your Claude account"**
  → a browser opens → sign in with **your** Claude (Pro/Max) account → approve → return to the
  terminal.
- If it drops straight into a chat without asking, type **`/login`** and pick your account.

## 4. Verify

```
claude -p "say OK"
```
If it prints **`OK`**, you're done — Claude is installed and signed in.

## 5. Open the app

Launch **CourseForge** or the **Lecture Wizard**. Its tools-check / launch screen will now show
**Claude detected** (green), and you can generate. It uses your Claude account behind the scenes
(your usage — no API key).

---

## Notes & troubleshooting

- **You need your own Claude Pro or Max subscription.** Generation runs on whichever Claude
  account is signed in on *your* machine — your usage, not anyone else's.
- The login is **one-time per machine** and stays signed in. If it ever expires (you'll see a
  *401* or *"claude exited 1"* during generation), just run `claude` → `/login` again.
- **`claude` is not recognized** right after installing → **close and reopen the terminal** so the
  PATH refreshes. If it still isn't found, reboot.
- **`npm` is not recognized** → Node.js isn't installed yet (or the terminal predates it) — do
  step 1 and reopen the terminal.

*Internal TSI / DILC.*

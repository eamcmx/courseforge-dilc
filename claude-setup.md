# Setting up Claude Code (the only requirement)

Both **CourseForge** and the **Lecture Wizard** generate content by driving **your own
Claude account** through the `claude` command-line tool — no API key, nothing shared. You
install it once per machine and sign in with your own Claude (Pro or Max) subscription.

> This is the **only** hard requirement. CourseForge ships with everything else bundled
> (Python and its libraries are inside the app — nothing else to install).

## 1. Install Claude Code

### Recommended — native installer (no Node.js needed)

In **PowerShell**, run:
```
irm https://claude.ai/install.ps1 | iex
```
That's it — the native installer has **no Node.js dependency** and keeps itself up to date.

*(Alternative: `winget install Anthropic.ClaudeCode`.)*

### Fallback — npm (only if you prefer it; this one DOES need Node.js)

If you'd rather install via npm, you must install **Node.js** first:

1. Download the **LTS** installer from **https://nodejs.org**, run it (accept defaults), then
   reopen PowerShell and check: `node --version` (any **v18+** is fine).
2. Install Claude Code:
   ```
   npm install -g @anthropic-ai/claude-code
   ```

> 💡 Most people should just use the **native installer above and skip Node.js entirely.**

## 2. Start Claude and sign in (with YOUR account)

In a terminal, run:
```
claude
```
- The first time, it walks you through login → choose **"Log in with your Claude account"**
  → a browser opens → sign in with **your** Claude (Pro/Max) account → approve → return to the
  terminal.
- If it drops straight into a chat without asking, type **`/login`** and pick your account.

## 3. Verify

```
claude -p "say OK"
```
If it prints **`OK`**, you're done — Claude is installed and signed in.

## 4. Open the app

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
- **If the native install fails** with a `403` or a curl/network error, see
  https://code.claude.com/docs/en/troubleshoot-install — or use the npm fallback above.
- **Git for Windows** is recommended (so Claude can use Bash); without it Claude falls back to PowerShell.

*Internal TSI / DILC.*

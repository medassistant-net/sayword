# sayword.ai Desktop — v0.6.0

**2026-10-19**

Command mode comes to the desktop app — plus a set of fixes that make dictation on macOS
reliable.

- **Command mode (early preview).** Hold **Left Shift** on Windows or **Right Shift** on
  macOS, say what you need — "добавь в правой доле печени кисту двенадцать миллиметров" — and
  release: a properly worded finding appears at the cursor instead of your words. The app
  never reads your document, so it inserts only what you dictated; when a request can't be
  carried out from your words, a clarifying question appears in the small window. Rebind the
  key or switch it off in Settings. More in [Command Mode: Say What You Need, Not What to
  Type](../notes/2026-10-19-command-mode-overview.md).
- **Text is inserted once — when you release the key.** It no longer appears in the document
  piece by piece mid-sentence. The start beep is no longer transcribed as a word.
- **Fixed: an expired sign-in failed silently.** The app now asks you to sign in again.
- **Fixed (macOS): presses of Right Cmd / Right Shift were cut off instantly** on recent macOS
  versions, so dictation never started.
- **Fixed (macOS): the dictation window was clipped and parked mid-screen** on Retina
  displays. When the cursor can't be found, it now appears at the bottom centre of the screen.
- **Fixed (Windows): text can no longer land in the wrong window.** If you switched to another
  window while it was being processed, the text goes to the clipboard, with a notice saying so.
- **Settings now save and apply immediately, without a restart.** The **Share diagnostic
  logs** button in Settings bundles the logs (which contain neither dictated text nor audio)
  for support.

The macOS build is signed and notarized by Apple (universal DMG, Intel + Apple Silicon). The
Windows installers (x64 and x86) are not yet code-signed — Windows SmartScreen will warn on
launch: choose **More info → Run anyway**.

[Download v0.6.0](https://github.com/medassistant-net/sayword/releases/tag/desktop-v0.6.0)

Feedback: [saywordai@gmail.com](mailto:saywordai@gmail.com).

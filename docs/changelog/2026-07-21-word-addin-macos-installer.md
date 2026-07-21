# Word Add-in — v1.1.1: One-Click macOS Installer

**2026-07-21**

Mac setup no longer needs Finder's "Go to Folder" dialog or a manual file copy. A
signed and Apple-notarized `.pkg` installer now does it for you.

- Download, double-click, **Continue → Install** — no admin password, no Gatekeeper
  warning (the installer is Developer-ID signed and notarized).
- It drops the manifest into Word's add-ins folder and quits Word automatically so it
  picks up the change on next launch. Activating the add-in (**Home → Add-ins →
  sayword.ai**) is still a one-time manual step in Word itself.
- Requires macOS 11 (Big Sur) or newer.
- The old manual wef-folder-copy method still works and is documented as a fallback.
- This build also carries manifest 1.1.1, with a corrected ribbon icon.

[Download the installer](https://github.com/medassistant-net/sayword-word-addin/releases/tag/v1.1.1)
· see the [installation guide](../howtos/2026-07-21-word-addin-installation.md) for the
full Mac walkthrough (Method A).

Feedback: [saywordai@gmail.com](mailto:saywordai@gmail.com).

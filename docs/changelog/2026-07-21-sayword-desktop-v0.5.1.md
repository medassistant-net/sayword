# sayword.ai Desktop — v0.5.1 (macOS)

**2026-07-21**

A macOS reliability release for the sayword.ai desktop app.

- **Fixed: silent (zero-filled) microphone audio.** The signed/notarized build now
  requests the hardened-runtime microphone entitlement and TCC authorization at launch,
  so dictation actually captures real audio instead of silence — the overlay waveform
  and transcripts were dead before this fix, even though no error was surfaced.
- **Lowered the minimum macOS version to 11.0 (Big Sur).** It was pinned to 13.0 with
  no API actually requiring it. The app now installs on older Intel Macs (Big Sur /
  Monterey), not just Ventura and newer.
- Windows is not part of this release yet (blocked on an EV code-signing certificate).

Signed + Apple-notarized universal DMG (Intel + Apple Silicon), verified with
`spctl`/`stapler`.

[Download v0.5.1](https://github.com/medassistant-net/sayword/releases/tag/desktop-v0.5.1)

Feedback: [saywordai@gmail.com](mailto:saywordai@gmail.com).

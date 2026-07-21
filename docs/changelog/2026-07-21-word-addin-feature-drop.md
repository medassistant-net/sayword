# Word Add-in — Feature Drop: One-Click Fixes, Dark Mode, Russian UI

**2026-07-21**

A round of updates to the sayword.ai Word add-in focused on making report verification
actually actionable, and on making the add-in feel like a native part of Word rather than
a bolted-on panel.

<div class="video-wrapper" style="position:relative;padding-bottom:56.25%;height:0;overflow:hidden;max-width:100%;">
  <iframe src="https://www.youtube.com/embed/6nMvE95TbQg" title="sayword.ai Word add-in — feature drop"
    style="position:absolute;top:0;left:0;width:100%;height:100%;border:0;"
    allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture"
    allowfullscreen></iframe>
</div>

## What's new

- **One-click fixes in Verify Report.** Issues that carry a suggested correction now show
  an **Apply** button — it swaps the flagged text for the suggestion, selects it, and marks
  the row done. The panel header tracks progress with a `N / M resolved` bar, and every row
  can be toggled done manually. Anchor matching is now tiered (exact → whitespace/punctuation
  tolerant → fragment) so a stray table border or line break no longer stops a fix from being
  located.
- **Dark theme.** The task pane now follows Word's own light/dark theme instead of always
  rendering light — no more glare in a dimmed reading room.
- **Russian + English interface.** All UI text now runs through a proper localization layer.
  Russian is the default and the interface auto-detects from Word's own display language —
  no manual switcher needed.
- **Refreshed branding.** The ribbon button now carries the real sayword.ai mic icon instead
  of the default Office add-in placeholder.

Setup hasn't changed — see the [installation guide](../howtos/2026-07-21-word-addin-installation.md)
if you haven't installed the add-in yet.

Feedback: [saywordai@gmail.com](mailto:saywordai@gmail.com).

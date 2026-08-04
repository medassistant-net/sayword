# Протоколы — v0.3.0

**2026-08-04**

An update to **Протоколы**. One change, and it was asked for: **a new batch of protocols can
now be added to a catalog the doctor is already working through.**

There was previously no path for this at all. Once the first pass finished, the app always
opened on the review screen and a second processing run was refused. Not by oversight: the full
pipeline re-groups protocols into categories and rebuilds the review queue from scratch, so it
would have reshuffled categories underneath the doctor and thrown away the queue they were
halfway through. What was missing was not a way around that guard but a mode that only adds.
That mode now exists.

## How it works

An **«Добавить протоколы»** button at the bottom of the category list: pick a folder, confirm
the number of files found, watch the progress.

The folder can be a new one, or the same one with more files dropped into it — the app
recognises protocols it has already processed and skips them. They are not processed again and
not billed again.

What is guaranteed to survive:

- **Approvals and rejections** — no stage touches them.
- **The categories of protocols already processed** — new ones are placed into existing
  categories by similarity, and a label is written only where there was none. An existing
  protocol cannot change category.
- **The current review queue** — it is only topped up to each category's quota; nothing
  previously selected is removed.

This was verified rather than asserted: on a copy of a 18,396-report catalog with 270 approvals,
every approval survived, no approved report changed category, and the queue grew from 972 to
1304.

Signed with a Developer ID and Apple-notarized (Apple Silicon) — it opens by double-click and
installs without an internet connection.

[Download v0.3.0](https://github.com/medassistant-net/sayword/releases/tag/protocols-v0.3.0)

Install guide (RU): [Протоколы — установка и работа](../howtos/2026-08-02-protocols-installation.md)

Built a catalog on an older version and seeing thousands of reports in the manual review queue, or meaningless category names? [How to rebuild it without losing your work (RU)](../howtos/2026-08-04-protocols-fresh-start.md)

Feedback: [saywordai@gmail.com](mailto:saywordai@gmail.com).

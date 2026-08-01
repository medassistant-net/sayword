# Протоколы — v0.1.0

**2026-08-02**

First distributable build of **Протоколы**, a macOS app for radiologists to review and
approve AI-categorized CT/MRI protocol reports before they go into a reference corpus for
downstream AI report drafting.

- **Signed, notarized, self-contained `.app`/`.dmg`.** No Docker, no separate installs —
  point it at your own DOCX folder and it runs entirely on your machine, with a browser-based
  UI for setup and review. Only redacted text is ever sent out, for AI categorization and
  quality scoring.
- **Local PII redaction before anything leaves the machine.** Names, birth dates, and similar
  personal data are stripped from each report before it is grouped into categories or scored.
  Anything the redaction pass isn't fully sure about goes into a review queue — a human has to
  confirm it before that report can be scored or exported.
- **AI-assisted categorization and quality scoring.** Reports are automatically grouped into
  pathology categories and scored 1–5 for completeness/clarity, so the doctor can focus review
  time on the best candidates in each category instead of reading everything.
- **Editable categories, redaction queue, keyboard-driven review** (approve/reject/skip,
  reassign category, search across the whole corpus).
- **Robust to network blips.** A dropped connection during the (batch) scoring step is retried
  automatically; if it fails outright, the next run picks up the already-submitted batch
  instead of resubmitting and double-billing for it.

macOS build is signed + Apple-notarized (Apple Silicon), verified with `spctl`/`stapler`.

[Download v0.1.0](https://github.com/medassistant-net/sayword/releases/tag/protocols-v0.1.0)

Install guide (RU): [Протоколы — установка и работа](../howtos/2026-08-02-protocols-installation.md)

Feedback: [saywordai@gmail.com](mailto:saywordai@gmail.com).

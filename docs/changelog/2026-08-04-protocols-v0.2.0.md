# Протоколы — v0.2.0

**2026-08-04**

Maintenance release for **Протоколы**, the macOS app radiologists use to review and approve
CT/MRI protocol reports. Two changes, both about not losing work: one recovers reports that
were being sent to manual review for no good reason, the other makes sure a decision the
doctor made stays made.

- **Header tables from other clinics' templates are recognised.** Field labels are now matched
  by word rather than by exact substring. A template phrasing a row as «Дата и время
  исследования» did not match the expected «Дата исследования», so the *whole* header table was
  rejected as unrecognised and the report landed in the manual review queue — not because
  anything was wrong with it, but because one row was worded differently. Matching stays
  exact-form rather than stemmed: «Модальности» still will not match «Модальность», and a label
  like that goes to review as before. That is deliberate — an unfamiliar label should fail
  toward human review, not toward a confident guess.

    Measured on a single-practice archive it recovers about 2.7% of the reports that were being
    flagged. On archives that mix templates from several sites — which is where this problem
    actually lives — the effect is larger.

- **Review decisions record who made them.** Approving or rejecting a report now stores that a
  person decided it, and resetting clears that again. Previously the automatic selection stages
  could not tell a doctor's judgement from their own machine-made stand-in, so a later run could
  overwrite a decision — including turning a rejection back into an approval and erasing the
  review timestamp with it. It cannot now.

Signed with a Developer ID and Apple-notarized (Apple Silicon), verified with `spctl` and
`stapler` — it opens by double-click, with no Gatekeeper workarounds, and installs without an
internet connection.

[Download v0.2.0](https://github.com/medassistant-net/sayword/releases/tag/protocols-v0.2.0)

Install guide (RU): [Протоколы — установка и работа](../howtos/2026-08-02-protocols-installation.md)

Feedback: [saywordai@gmail.com](mailto:saywordai@gmail.com).

# Reports in the Doctor's Own Style, Ready-Made Norm Wordings, and Command Mode

**2026-08-29**

Three updates that are best read together, because they are all the same thing: getting the
system to write the way a radiologist writes, rather than the way it thinks is correct.

## Conclusions are now the length a doctor writes

A generated conclusion used to run about four times longer than the doctor's own — thorough,
smooth, and unlike a real report. Each anatomical area now carries its own house style, drawn
from real reports: how long a conclusion runs, what order the organs come in, which turns of
phrase are used, what gets abbreviated and what is written out.

Measured across the same 30 reports before and after:

- **Conclusion length** — from 1,736 characters down to 992. The doctors' own median, across the
  whole catalog, is 444.
- **Share of conclusions longer than 90% of the doctors'** — was 87%, now 47%, and on the
  shortest of the paths 7%.
- **Invented measurements** — present in 14 reports out of 15, now 0 out of 15. The system no
  longer attributes a size, a contour or a state of the surrounding tissue to an organ when the
  input says nothing about it, and it no longer strengthens the doctor's own wording (an
  "enlargement" does not become a "hypertrophy").
- **Markup matches the doctor's document** — the organ name in bold inside the paragraph, not a
  heading per organ. We checked this against the doctor's original `.docx`: not a single heading
  style in it, every paragraph plain.

An honest caveat: all of the above is about form and about facts surviving intact. Clinical
quality is not what these numbers measure. Only blind comparisons against doctors' own
conclusions can settle that, and those are still ahead.

## Ready-made norm wordings

There is now a store of house wordings: how the normal finding for a given organ actually reads
in real reports, selected by how closely the corpus agrees on it word for word.

The practical difference is simple. "Spleen, normal" is no longer composed from scratch — the
ready-made paragraph is inserted, the one that repeats verbatim across dozens of reports. The
answer is immediate, with no trip to the AI at all.

- **Coverage after the corpus rebuild:** CT — 80 area-and-organ combinations out of 120 (was
  25); MRI — 62 out of 75 (was 11).
- **"Bronchi, normal" works for the first time** — 358 reports agree on one wording verbatim.
- If the corpus yielded a single line rather than a full description of the organ, the system
  says so: this is one line, not the whole paragraph. Presenting them alike would promise a
  completeness that is not there.
- For seven organs the insertion is **deliberately switched off**: the labelling of that data is
  wrong, and instead of a plausible-looking wrong paragraph the system explains what is wrong
  and what to do instead.

## Command mode — in the Word add-in

The add-in now has a **Dictate / Command** switch. In command mode the doctor speaks not text
but an instruction about the document:

- "insert spleen, normal"
- "remove the italics in the first paragraph"
- "swap the first and last paragraphs"
- "delete the last sentence"
- "shorten this"

How it behaves:

- **One command, one undo.** Ctrl+Z returns the document to its state before the command, in
  full, and does not swallow what the doctor typed before it.
- **The selection's markup survives.** If an organ label was bold, it comes back bold. The
  system may change formatting only when the spoken instruction asks for it.
- **Positional references are resolved inside the selection.** "The first paragraph" means the
  first of the selected ones, not the first in the document.
- **Content does not change.** When reworking a selection the system may change wording and
  order, but every finding, every organ and every measurement must survive. If carrying out the
  instruction would require adding or dropping a fact, that is grounds to ask rather than to
  act.
- **An instruction it cannot resolve is not guessed at** — it asks. A refusal is visible
  immediately; a quietly mangled paragraph is not.

**The web editor is coming.** The web and the add-in share the same server side, the client-side
pieces are written, and the editor's buttons are moving onto them.

**The desktop app is coming too.** There, command mode will be insert-only: by design the
desktop app does not read the document you are working in, and that constraint stays.

## About our template corpora — please read

Everything above rests on our corpora of templates. They deserve a plain description.

- **These are experimental stores.** They were assembled to test a hypothesis — that the system
  can be taught to write in the house style by being shown how the house writes. The hypothesis
  is holding up, but the state of the corpora is working, not final.
- **The corpus is not built from your dictations.** It is an archive of anonymised templates
  spanning a range of pathologies and study areas, not what you dictated into sayword.ai:
  dictated text and audio are not stored and never enter the corpus. Every template passes an
  automatic personal-data check before it can go in; the ones the check flags stay out until a
  person has reviewed them. Dates are generalised and file names hashed.
- **The templates in them vary in quality.** The archive comes out of real practice and is
  uneven for that reason: an exemplary description sits next to a careless one. Selection is
  automatic and formal, and it cannot tell good from merely usual.
- **No template has been reviewed by a doctor.** No anatomical area has been signed off by a
  radiologist yet. That is why, wherever text comes from the corpus, the client shows a badge:
  **provisional wording, not confirmed by a radiologist**. Hiding it would be dishonest — it is
  the only way to tell what has been reviewed from what a machine picked out.
- **Coverage is incomplete.** For some organs there is no ready wording at all, and for seven
  the insertion is switched off on purpose because the data labelling there is wrong. In those
  cases the system says it has nothing to insert rather than composing something plausible.
- **The corpora will grow.** Doctors are working through the base; as areas are approved the
  provisional badge will disappear area by area, with no app update, and wording coverage will
  rise. We have already rebuilt the corpus once, and it produced a jump in coverage: CT from 25
  combinations to 80, MRI from 11 to 62.

All of which comes down to one practical rule, unchanged: **responsibility for the content of a
report stays with the doctor.** The system prepares the text; the doctor signs it.

That covers where the text comes from. How the data you send us is processed — where speech
recognition runs, and what that means for 152-ФЗ and medical confidentiality — is the subject of
a separate standing disclaimer published in the community channel. It remains in force in full.

Feedback: [saywordai@gmail.com](mailto:saywordai@gmail.com).

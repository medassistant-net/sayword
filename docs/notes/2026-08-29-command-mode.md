# Command Mode: Your Voice Can Now Edit, Not Just Dictate

**2026-08-29** · Article 1 of 3

Until now, your voice did one thing in sayword.ai: it turned speech into text. Everything else —
moving a paragraph, cutting a sentence, inserting an organ's normal finding — stayed manual.

The Word add-in now has a second mode. In it you say not the text but **what to do with the
document**, and the document changes on its own.

This is the first of three articles. August brought a lot of change, and dumping all of it at
once would not respect your time. We start with what you can try today.

## Turning it on

Next to the record button there is now a switch: **Dictate** and **Command**.

1. Switch to Command **before** you start recording — the switch is locked while recording, so
   it cannot cut off what you have already said.
2. Press record and speak the command in your normal voice.
3. Stop talking. After a couple of seconds the command runs; a countdown on screen says
   "Running the command in N s — keep talking to add to it."

That last point matters more than it looks. The pause is not a patience timer but a way to
extend what you said: while you speak, the countdown resets. Change your mind halfway through —
finish the sentence, and the system hears the whole thing.

If the command is about a specific piece of text, **select it first**. Almost every rule below
rests on the selection.

## What you can say

### Insert an organ's normal finding

> "insert spleen, normal" · "add adrenals, normal" · "write in bronchi, normal"

The most frequent command, and the fastest one: a ready-made wording is inserted, taken from the
corpus of reports — the one that dozens of descriptions agree on almost word for word. Nothing
is composed on the spot, and the answer is immediate.

Say it however it comes out. Russian case endings and the ё/е spelling difference are all
understood the same way. Politeness — "insert the spleen normal here, please" — does not get in
the way.

### Transform the selection

> "format this" · "tidy it up" · "shorten" · "expand" · "rephrase"

A broadly worded request is fine. If your words make it clear what to do, the system does it
rather than asking. "Format this" over a selected paragraph means "bring it to the style
accepted for this area, losing nothing."

### Reorder

> "swap the first and last paragraphs" · "put these in order"

The order changes; the content does not.

### Delete a fragment

> "delete the last sentence" · "drop the bit about the kidneys"

### Fix a fragment

> "correct the previous sentence"

### Change the formatting

> "remove the italics in the first paragraph" · "make this bold"

This is the only case where the system may change markup — when you explicitly ask. Everywhere
else it preserves it.

## Five rules worth knowing

These are not about the interface but about how the system reasons. Knowing them, you will phrase
commands more precisely — and understand why you sometimes get a question instead of an action.

**1. "The first paragraph" means the first of the selected ones.** Not the first in the
document. You made a selection precisely in order to talk about it. With no selection and a
positional reference, the system asks rather than guessing across the whole document.

**2. The smallest necessary thing is touched.** Ask to delete one sentence inside a selected
paragraph and the sentence goes, rather than the paragraph being rewritten. Rewriting a whole to
fix a part means needlessly running text you did not ask to change through the system. The
smaller the blast radius, the less can go wrong.

**3. Wording changes, content does not.** In any transformation of a selection, every finding,
every organ and every measurement must survive. If the request could only be carried out by
adding or dropping a fact, the system asks. This is its central prohibition.

**4. Markup comes back as it went in.** An organ label that was bold returns bold. Flat text in
answer to marked-up text is the same kind of loss as a dropped measurement, only less immediately
visible.

**5. One command, one undo.** Ctrl+Z returns the document to its state before the command, in
full. And it does not swallow what you typed beforehand.

## What command mode cannot do yet

Better to read this now than to conclude something is broken later.

- **For seven organs the normal-finding insertion is switched off on purpose.** The data
  labelling for them in the corpus is wrong, and instead of a plausible-looking wrong paragraph
  the system explains what the problem is. "Insert liver, normal" answers with a refusal and an
  explanation rather than pasting someone else's text. This gets fixed on the corpus side, not
  in the app.
- **A repeated fragment is refused.** If what you ask to delete or fix occurs twice in the
  document ("not enlarged", "unremarkable"), the system will not guess which one. Select the
  right spot and repeat.
- **A positional reference with no selection gets a question.** See rule 1.
- **Two requests in one utterance** ("add spleen normal and format the rest") will be carried
  out, but more slowly: the fast path is not built for that, and the whole utterance takes the
  long road. Previously the second half was silently dropped — that was the real problem, and it
  is gone.
- **The web editor and the desktop app are coming.** In the desktop app command mode will be
  insert-only: by design it does not read the document you are working in, and that constraint
  stays.

## Why we built it

Four goals, and an honest account of each.

**Let the voice steer the document, not only fill it.** No client of ours had this before. The
Word add-in has it now.

**Get the knowledge of normal findings out of the code.** Normal-finding wordings used to be
written into the program itself: they could not be extended without shipping a new version, and
the rest of the product could not see them. They now live in the corpus of reports — shared
across clients and extensible without an app update. After the very first rebuild of the corpus,
coverage went from 25 area-and-organ combinations to 80 for CT, and from 11 to 62 for MRI;
"insert bronchi, normal" worked for the first time.

**Make the most frequent command instant.** Done: inserting a normal finding answers
immediately, with no trip to the AI. As a side effect, seconds are no longer spent on hopeless
cases — "insert liver, normal" used to think for eight seconds before answering "please
clarify"; now it answers at once and says why.

**Don't damage the document quietly.** This turned out to be the most important one. The first
live test was brutal: a radiologist dictated five commands he would say without thinking, and
four of the five came back "an error occurred". All five work now. But the lesson of that session
was not that five commands got fixed — it was what the default behaviour has to be: **a refusal
beats a silent mistake.** A command it cannot resolve is not guessed at; the system asks. You see
a refusal immediately; a quietly mangled paragraph you find a week later.

## About the "provisional wording" badge

Wherever inserted text came from the corpus, you will see a badge: **provisional wording, not
confirmed by a radiologist**. The corpus was selected automatically, and no anatomical area has
been signed off by a doctor yet. As doctors work through the base, the badge will disappear area
by area — with no app update.

And the rule that changes neither with the mode nor with the version: **responsibility for the
content of the report stays with the doctor.** The system prepares the text; the doctor signs
it.

## Later in this series

- **Article 2 — how the system knows "how it is done here."** Why a generated conclusion used to
  run four times longer than yours, and what changed when every anatomical area got a style of
  its own.
- **Article 3 — your own reports.** The Протоколы app, building a corpus from your own archive,
  and how you can take part.

Try it and tell us what does not work: [saywordai@gmail.com](mailto:saywordai@gmail.com). A
command that was refused where it should have worked is the most useful thing you can send us.

# Command Mode: Say What You Need, Not What to Type

**2026-10-19**

!!! warning "Early preview"

    Command mode is open as a preview. It works, but not always: some commands may behave
    differently from what is described below, or not work at all. The wording of commands will
    change. We keep the mode open so that you run into this and tell us — for how, see [the end
    of the article](#if-something-goes-wrong).

Ordinary dictation turns your words into text: what you say is what gets typed. In **command
mode** you don't say the words to insert — you say **what you need**, and the document receives
the finished result instead of your phrase.

Command mode is available in two places: the Word add-in and the sayword app for Windows and
macOS. Below: what it gives you, where and how to use it, and why it behaves the way it does.

## What it gives you

- **Less switching.** No need to look away from the images to grab the mouse, find the paragraph
  and fix it by hand — just say it.
- **Consistent wording.** Text arrives in the accepted form of a description, not the way the
  phrase happened to come out.
- **One habit everywhere.** The same technique works in Word and in any other program where you
  write a report.
- **Text doesn't jump while you're talking.** The result is inserted once, in full, when you've
  finished — not piece by piece in the middle of a sentence.

## Where it works

| | Word add-in | sayword app |
|---|---|---|
| Where | In a Word document | In any window: a RIS/PACS report field, email, any text field |
| How to turn it on | The «Диктовка / Команда» (Dictate / Command) switch | A separate key for commands |
| When it runs | A couple of seconds after you pause | When you release the key |
| Insert new text | Yes | Yes — from what you dictated |
| Edit, delete, rearrange existing text | Yes | No |

### In Word

Next to the record button there is a **«Диктовка / Команда»** (Dictate / Command) switch. Set it to
Command
**before** you start recording, say the command and stop talking. After a couple of seconds it
runs; if you keep talking, the command is extended. If the command is about a specific
fragment, **select it first**.

> "insert spleen, normal" · "shorten" · "expand" · "format this"
>
> "swap the first and last paragraphs" · "delete the last sentence" · "make this bold"

Whatever you ask for, the content survives — the wording changes, not the findings and
measurements. The formatting stays as it was too, unless you explicitly ask to change it. One
Ctrl+Z undoes the whole command. If a command is unclear, the system asks rather than guesses.

### In any window: the sayword app

In the sayword app, **version 0.6.0 or newer**, you have two keys:

| | Windows | macOS |
|---|---|---|
| Dictation | Right Ctrl | Right Cmd |
| Command | Left Shift | Right Shift |

Hold the command key, say what you need, and release it — the result appears where the cursor
is. While the command is being processed, a small window at the cursor or at the bottom of the
screen shows "Обрабатываю…" ("Processing…"); any answer or clarifying question appears in that
same window. The key can be rebound in the app's Settings, and command mode can be switched off
there as well.

Here command mode **only inserts new text** — and only from **facts you say out loud**:

> "add a twelve-millimetre cyst in the right lobe of the liver" — a properly worded finding is
> inserted.
>
> "add a normal description of the liver" — the app asks a clarifying question: it does not see
> your document and will not invent anatomy you didn't name.

For the same reason, editing, deleting or rearranging text that's already written is something
you do in Word, not in the app.

## Why it's built this way

**Privacy.** The sayword app never reads what's on your screen. Only your spoken words are sent
— and only to your own sayword account.

**Facts come from your words.** The system won't add a finding, size or location you didn't
say. It can word what you said, but it won't write in what you didn't.

**It would rather ask than spoil.** A refusal or a question you see immediately. A quietly wrong
paragraph you'd find a week later — or not at all.

## The "provisional wording" note

Some of the ready-made wording comes from a shared phrase base. That wording was selected
automatically and **has not yet been confirmed by a radiologist**, and the app marks it as such:
in Word a "Provisional wording — not confirmed by a doctor" note appears; in the sayword app,
"source not confirmed" appears in the same small window. As doctors work through the base, the
note will disappear.

## Limitations

- **A repeated fragment** (Word). If what you ask to delete or fix appears twice in the
  document, the system asks you to select the right one.
- **Two requests in one phrase** (Word) both run, but more slowly.
- **The app doesn't edit existing text or write full normal descriptions.** It inserts only
  what you dictated.
- **This is an early preview.** Some commands may fail, and the wording of commands may change.
- **On Windows, Right Shift is a poor choice for commands.** Holding it for 8 seconds turns on
  the system Filter Keys feature. That's why Left Shift is the default.

## If something goes wrong

- **Word:** press the **"Report an issue"** button in the task pane right after the failed
  command, and add a short note in the comment field saying what you expected.
- **sayword app:** the **"Report a problem…"** item in the menu of the sayword icon in the
  system tray (Windows) or the menu bar (macOS).
- **Email:** [saywordai@gmail.com](mailto:saywordai@gmail.com).

A command that was refused where it should have worked is the most useful thing you can send
us.

And the rule that changes neither with the mode nor with the version: **responsibility for the
content of the report stays with the doctor.** The system prepares the text; the doctor signs
it.

# TNA animations for computing education

**Live:** <https://lamethods.org/tna-cs-animations/>

Five self-contained, stepped animations about **where sequence data comes from** in
computing education, and what each source makes you decide before a transition network
can be estimated.

Each file is a single HTML page with no dependencies, no build step and no network
calls. Open it in a browser, or serve the folder and link to it from slides.

| | file | what it shows |
|---|---|---|
| **3a** | [`3a_source_autograder.html`](3a_source_autograder.html) | **Automated assessment.** A student edits, runs and submits in an online judge. Every action is a row in the log, interleaved in the order it happened, and the sequence is read straight off it. |
| **3b** | [`3b_source_ai_dialogue.html`](3b_source_ai_dialogue.html) | **Coded discourse.** A student debugging recursion with an AI assistant. A turn is not a state until a codebook is applied; at the end, coding only the student collapses every assistant turn to a single `AI`. |
| **3c** | [`3c_source_observation.html`](3c_source_observation.html) | **Observation.** Screen capture and think-aloud from a pair debugging a loop. One coder draws segment boundaries; a second coder draws different ones from the same tape. |
| **3d** | [`3d_source_sensors.html`](3d_source_sensors.html) | **Sensors.** Eye tracking over a spec, some code and a failing test. Gaze becomes states only once areas of interest are drawn and a minimum dwell is chosen — raise it and the short glances stop existing. |
| **3e** | [`3e_sequence_units.html`](3e_sequence_units.html) | **Building the sequences.** The same exercise as 3a, now across three students, two classes and two exercises — showing how `actor`, `session`, `order` and `timestamp` turn one flat log into 3, 5 or 6 sequences. |

## The argument

TNA needs the same three things whatever the source: **an actor**, **an order** and
**a state**. What changes is who supplies them — the machine, a coder, or an observer —
and that decides which arguments are free and which are a judgement call.

Reading 3a → 3d, meaning gets richer and scale collapses. A log hands over millions of
events that mean nothing on their own; a think-aloud hands over a few hundred that mean
something because a person decided they did.

3e is the companion to 3a: once you have the states, you still have to decide what
counts as *one sequence*. The same fifteen rows give three, five or six sequences
depending on where the cuts go, and every transition probability rests on that choice.

## Controls

All five share the same controls:

- **‹ Back · Play/Pause · Next ›** — or the **← → arrow keys** and **space**
- **step dots** to jump straight to a step
- **Speed** 0.5× to 2× — 0.5× is comfortable for narrating over
- **Autoplay** on by default; untick it and **Next ›** advances one step at a time,
  which is what you want when presenting
- **Loop** off by default; each ends on its final frame

Each step also writes a plain-text caption to an `aria-live` region for screen readers.

## Using them in a talk

Untick **Autoplay** and drive with the arrow keys, or set **Speed** to 0.5× and let a
step play while you talk over it. The final frame of each is the one to leave up — it
carries the `actor · order · state` summary.

## Notes on the content

The scenarios are illustrative but the shape of the data is not invented: the state
vocabularies, the ordering traps and the sequence-unit arithmetic follow real public
computing-education datasets. In particular 3a and 3e use an online judge that records
edits alongside runs and submissions, so a sequence needs no reconstruction — only a
decision about what counts as one.

No student data of any kind appears in these files. Every name, identifier, timestamp
and utterance is fabricated for the illustration.

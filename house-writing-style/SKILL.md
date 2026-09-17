---
name: house-writing-style
version: "1.0"
published: true
published_date: "2026-09-17"
claude_science_id: "skill_019bfsRfnmWaWCxMYuiZsVZV"
description: "House style for prose written for this user: bottom-line-up-front, plain ELI5 language, bold key terms, scannable structure, progressive disclosure. Load this before drafting any explanation, answer, summary, report, README, logbook entry, or markdown deliverable — it governs how the writing reads, so consult it at the start of writing rather than rewriting afterwards. Use it whenever you are about to write more than two or three sentences of prose for this user, even when they did not mention style, formatting, or writing."
---

# House Writing Style

**Applies to:** prose in chat, and written markdown deliverables (reports,
READMEs, logbook entries, summary documents, issue and commit descriptions).

**Does not apply to:** code comments and docstrings, and slide or talk text.
Those follow their own conventions unless the user asks otherwise.

## The one-line version

Answer first, in plain words, then the details — laid out so the reader can
skim it in ten seconds and know whether to read further.

The reason this matters: the reader is almost always scanning to decide what to
do next. Prose that withholds the conclusion until the end, or hides it inside
a dense paragraph, forces them to do work that the writer should have done.

## 1. Bottom line up front

Open with the direct answer or a one-sentence summary. Everything else is
support for that opening line.

- If the answer is a number, lead with the number.
- If the answer is "no" or "it depends", say so in the first clause — then say
  what it depends on.
- If the answer is uncertain or the data cannot settle it, that *is* the bottom
  line: **"Not determinable from this dataset"** is a direct answer.
- BLUF does not mean dropping the caveat. Put the single caveat that changes
  how the headline should be read immediately after it, then move on.

Do not open with restated context ("You asked about..."), with the method, or
with a narration of the work. The reader knows what they asked.

## 2. Plain language first, precise term second

Explain the idea in words that would work for someone outside the field, then
name the technical term once so the reader can look it up and so the prose
stays searchable.

> The model's confidence is badly calibrated — it says 90% when it is right
> about 60% of the time. The standard measure of this gap is the **expected
> calibration error**.

This ordering is the whole trick: plain sentence, then the term. It keeps the
text readable without making it vague.

What plain language is **not**: it is not lower precision. Keep exact numbers,
units, and conditions. Simplify the vocabulary, never the content. If a
simplification would make a statement false, state the real thing and add one
sentence explaining it.

Avoid: cryptic compression, poetic or literary phrasing, and academic register
for its own sake ("it is worth noting that", "one might consider", "a rich
landscape of"). Write the sentence you would say out loud.

## 3. Make it scannable

- **Bold the key terms** — the words a reader skimming for the answer needs to
  land on. Bold a term or a short phrase, not whole sentences. If half the
  paragraph is bold, none of it stands out.
- **Short sentences.** One idea each. Break a sentence that needs two commas
  and a semicolon into two sentences.
- **Bullets for anything enumerable** — options, steps, findings, caveats.
- **No walls of text.** Three or four sentences is a paragraph; more than that
  wants a break, a bullet list, or a sub-heading.
- **Tables** when the content is genuinely two-dimensional (options × criteria,
  runs × metrics). A table that has one column is a list.

## 4. Progressive disclosure

Structure every piece of writing so the reader can stop early and still have
what they need:

1. the bottom line,
2. the high-level shape of the reasoning or result,
3. the technical detail, parameters, and edge cases,
4. the things that did not work or do not matter yet.

Someone reading only level 1 should not be misled. Someone reading all four
should not find contradictions between them. In a longer document this maps
directly onto headings — put the summary above the first heading.

## 5. No silent assumptions

If a question has more than one reasonable reading:

- **Different readings imply different work** (different dataset, different
  method, a decision that is expensive to redo) → ask, with concrete options.
- **Different readings only change the explanation** → answer the most likely
  reading fully, then name the other in one line: *"If you meant X instead, the
  short answer there is Y."*

Never resolve an ambiguity silently and never leave it hanging. Both leave the
reader unable to trust the answer.

## Worked examples

**Example 1 — a chat answer.**

Before:
> I ran the sweep over the coupling parameter and after examining the resulting
> loss landscape it became apparent that there are several interesting features
> worth discussing, which I will describe below, and which may relate to the
> barren plateau literature.

After:
> **The loss flattens out above λ = 0.4** — gradients drop by about two orders
> of magnitude, which is the signature of a **barren plateau**. Below 0.4 the
> sweep looks healthy.
>
> Details: 40 points, 8 seeds each, gradient norms in `results/tables/lam_scan.csv`.

**Example 2 — a section heading in a report.**

Before: *"Considerations Regarding the Observed Discrepancy"*

After: *"Why the fitted mass is 3σ off the reference value"*

The heading should carry information, not announce that information is coming.

## Self-check before sending

Four questions, in order:

1. Does the first sentence answer the question?
2. Could a non-specialist follow the first paragraph?
3. Can I find the key numbers by skimming, without reading sentences?
4. Is there a claim here that assumed one reading of an ambiguous request?

If any answer is no, fix that before adding anything new.

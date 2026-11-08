---
name: technical-writing
description: Use when writing, editing, or reviewing user-facing documentation, help articles, READMEs, in-app microcopy, release notes, error messages, landing pages, SEO metadata, or comparison pages, or when removing AI slop from product and technical prose.
---

# Technical writing

The register is **plain, direct, and unbylined**. The reader is mid-task and wants to finish.
Nobody's personality should be between them and that.

The rules below are synthesized from established technical-writing authorities rather than
existing AI-generated copy: the Google developer documentation style guide, the Microsoft
Writing Style Guide, the 18F Content Guide, and Diátaxis. See `references/style-authorities.md`
for the sourcing, citations, and how conflicts between the guides were resolved.

## The voice

Four adjectives, in priority order. When two conflict, the earlier one wins.

1. **Accurate** - every claim is checkable against the code or a primary source. This outranks everything, including tone.
2. **Direct** - the reader gets the action or the fact in the first sentence.
3. **Plain** - everyday words, short sentences, no jargon the reader didn't bring.
4. **Respectful** - the reader is competent and busy, not a novice to be reassured.

Voice is constant; tone varies with the reader's situation. Someone deleting data, someone
comparing tools, and someone landing on a homepage are in three different emotional states,
and the copy should meet each one where it is - without changing who is speaking.

## Two registers

Pick one before writing. The technical register is the default; conversion is the exception.

|  | **Technical** (default) | **Conversion** |
|---|---|---|
| Where | help articles, docs, READMEs, in-app text, errors, compare pages, release notes | hero, landing sections, CTA blocks, About |
| Job | let the reader act or decide correctly | get the reader to start or try the product |
| Exclamations | none | allowed, one per block: "Start now!" |
| Questions | rare; only as a heading a reader would type | fine as section headlines |
| Superlatives | none | established brand tagline only |
| Voice/person | second person, present tense, active | same |

The conversion register relaxes exactly those three rows. Everything else below applies to
both.

## Rules

**Person and tense**

- **Second person.** "You", "your team", "your project". Address the reader directly.
- **No first person.** No "I", and no "we"/"our"/"us"/"let's" outside an About page's
  origin story. Name the product or system as the subject: "The app sends a reminder", not "we send".
- **Present tense.** Describe what happens, not what will happen. *"Your changes go live"*,
  not *"your changes will go live"*. Cut "will" on sight.
- **Active voice.** Name who acts. *"Save the recovery key"* beats *"the recovery key should
  be saved"*. Test: if you can append "by zombies" and it still parses, it's passive.
  Passive is acceptable only to soften an error or when the actor is genuinely irrelevant.

**Words**

- **Use contractions.** "Don't", "you'll", "it's", "can't". All three source guides call for
  them; formality without them reads stiff, not authoritative.
- **Everyday words.** *use* over *utilize*, *tell* over *inform*, *most* over *the majority of*,
  *enough* over *a sufficient number of*, *to* over *in order to*, *before* over *prior to*.
- **"For example", not "e.g." "That is", not "i.e."** Spell out Latin abbreviations.
- **No internet shorthand** in product copy: tl;dr, IMO, FWIW, YMMV.
- **Cut intensifiers and hedges**: just, simply, very, really, actually, of course,
  obviously, easily, seamlessly, effortlessly, instantly. "Simply click Save" tells a stuck
  reader the problem is them.
- **No unverifiable claims**: best, easiest, simplest, most powerful, lightning-fast, the only tool that.
- **Timeless phrasing.** Avoid "currently", "new", "soon", "latest" - they date the page and
  imply a roadmap. Write "TaskGrid doesn't include time tracking", not "doesn't currently".
- **Don't anthropomorphize.** Software doesn't "know", "want", or "see". It stores, sends,
  shows, validates.
- **Positive framing.** Say what the reader can do. *"Sign in to continue"*, not *"You can't
  continue without signing in."*

**Sentences and structure**

- **Under 30 words per sentence.** One idea each. Split stacked clauses.
- **Start with the verb or the goal.** *"To share your project, copy the link"* - the
  condition first, then the action.
- **Sentence case for every heading and title.** "Create your first project", not
  "Create Your First Project". No acronyms in headings, no trailing punctuation.
- **Consistent heading grammar** across a set: all noun phrases, or all imperative verbs.
  Never mixed.
- **Two- or three-sentence intro** under the title so the reader can confirm they're in the
  right place before reading further.
- **Tables only for data** - two or more rows sharing two or more columns. Not for layout.

**Punctuation**

- **Em dashes take no spaces** when used at all: `word—word`. Prefer a period or a comma;
  an em dash usually marks a sentence that wants to be two.
- **Parentheses, semicolons, and ellipses: sparingly.** A parenthetical aside is usually a
  second sentence in disguise.
- **Spell out ordinals** (first, not 1st). **No "(s)" plurals** - write "items" or "one or
  more items".

**Instructions**

- **Name UI elements exactly** as they appear on screen, in **bold**: click **Add Row**.
  Verify the label in the code before writing it; never invent buttons, dialogs, or steps
  that aren't in the UI.
- **Match the verb to the control**: *choose* from a menu (*"From the **Board** menu, choose
  **Export CSV**"* — not *"Click **Board**, then click **Export CSV**"*), *select* or
  *clear* a checkbox, *click* or *tap* a button, *follow* or *open* a link, *enter* text in a
  field.
- **One action per step.** If a step has an "and" in it, it's two steps.
- **State the condition before the action**, so the reader can skip steps that don't apply:
  *"If your export includes archived rows, select **Include archived**."*
- **Don't document the obvious.** "Log in to your account" as step one of everything is
  filler. Start where the reader's actual problem starts.
- **Backticks for anything typed or copied verbatim.**

## Documentation modes (Diátaxis)

Decide which of the four a page is before writing it, and don't mix them. Two questions
settle it: does the content inform **action** or **cognition**, and does it serve the
**acquisition** or the **application** of skill?

| | Acquisition | Application |
|---|---|---|
| **Action** | tutorial - a lesson, complete end to end | **how-to guide** - directions toward a goal |
| **Cognition** | explanation - background and why | reference - propositional facts about the machinery |

Most help center and operational documentation is a **how-to guide**. That has consequences:

- **Name it by the reader's goal, not the feature.** "Reset a team member's password", not
  "Using the Security tab". A how-to answers a human task.
- **Action and only action.** No teaching, no digression. If background matters, link to it.
- **Completeness is not the goal** - usability is. Start and end somewhere meaningful and
  let the reader join it to their own work.
- **Stay adaptable.** A guide useful for exactly one narrow case is rarely worth writing.
- **Order for flow**, not for the order the UI happens to present things.

A comparison page, CLI flag table, or API spec is **reference**. Release notes are
**reference**. A homepage is marketing and sits outside the framework.

## Positioning and comparisons

When comparing your product or tool to an alternative, argue from sourced facts rather than
adjectives:

- **State limitations plainly**, in the same flat sentence style as capabilities:
  *"TaskGrid doesn't include Gantt charts or time tracking."* No "coming soon", no reframing
  the gap as "focus" or "avoiding bloat" in the same sentence.
- **Give the alternative a real recommendation.** Write the "choose them when…" section
  first, and make it one their own author or marketer would sign off on. It's what makes the
  rest of the comparison credible.
- **Link every external claim** to the alternative's own pricing page or documentation,
  inline. If you can't source it, cut the claim.
- **Never disparage.** Cut "bloat", "steep learning curve", "clunky", and "over-engineered".
  The strongest permitted edge is a sourced fact.

## Common structures

**Help article / how-to guide**: `heading` (sentence case, goal-named) → `intro` (two or
three sentences: what this accomplishes, and when you'd want it) → `steps` (one action each,
imperative verb matched to control, exact UI label bolded, condition before action) →
`callout` (`note` / `tip` / `warning`, optional) → `next step` (point to a related article,
template, or support).

**Compare page**: `intro` → `comparison table` (factual rows) → `decision guide` (when to
choose your tool vs when to choose the alternative) → `summary` → `FAQ` (include "When
should I choose [alternative] instead?").

**Landing section**: one audience per block - a headline naming their situation, two
sentences of literal mechanics, a button/CTA.

**SEO**: `page_title` is plain ("Product A vs Product B"). `meta_description` runs 150-160
characters, says what the page does, and names the audiences.

**Error and confirmation microcopy**: consequence first, then mechanism, then the way out.
*"This action cannot be undone. The project and all its data are permanently removed."*
No apology, no reassurance, no blame.

## Never

- **"It's not X, it's Y"**, "isn't just X - it's Y", "less about X, more about Y", and
  decorative rule-of-three ("for reporting, archiving, or offline analysis").
- **LLM register**: delve, landscape, tapestry, seamless, robust, comprehensive, unlock,
  empower, elevate, leverage (as a verb for "use"), streamline, lightning-fast, "designed to
  help you", "designed for", "whether you're a ___ or a ___", "in today's ___", "built for
  teams that just need to get things done".
- **Unverified product claims** not checked against the codebase, or competitor claims
  without an inline link to primary documentation.
- **Personal opinion or story** outside an About page.

## Workflow

1. Name the register (technical or conversion) and, for docs, the Diátaxis mode.
2. Write the reader's goal as a sentence before writing anything else. If you can't, you
   don't have a page yet.
3. Verify consistent domain and UI terminology against the codebase before drafting.
4. Draft the action or the fact first; add framing only if it earns its place.
5. Verify every product claim against the code and every external claim against a live
   source.
6. Run `references/revision-checklist.md`.

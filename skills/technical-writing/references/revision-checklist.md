# Revision checklist - Technical writing

Work top to bottom. Accuracy failures block; style failures get fixed.

## 1. Accuracy

- [ ] Every product or system capability claim is **verified against the code**, not assumed.
- [ ] Every external or competitor claim **links to primary documentation** — pricing page
      or official docs — inline in the sentence.
- [ ] Limitations are stated in the same flat style as capabilities: *"TaskGrid doesn't
      include time tracking."* No "coming soon", no reframing the gap as focus or lack of bloat.
- [ ] Any competitor or alternative recommendation is one **their own author or marketer
      would sign off on**.
- [ ] Every UI label, CLI flag, or config key in an instruction **matches the code**,
      exactly.

## 2. Mode and register

- [ ] The register is named and consistent — technical or conversion, not drifting between.
- [ ] For a doc page, the **Diátaxis mode** is one thing: a how-to guide guides action and
      doesn't teach; reference states facts and doesn't instruct.
- [ ] A how-to is **titled by the reader's goal**, not by the feature or menu it uses.
- [ ] The reader's goal is stated in a sentence somewhere in the first three sentences.

## 3. Grammar and person

- [ ] **Second person** throughout ("you", "your"). No "I". No "we"/"our"/"us"/"let's"
      outside an About page.
- [ ] **Present tense.** Search for "will" and cut it.
- [ ] **Active voice.** Apply the "by zombies" test to anything that reads limp.
- [ ] **Contractions used** — don't, you'll, it's. Stiff uncontracted prose is a defect.
- [ ] **No sentence over 30 words.**
- [ ] **Sentence case headings**, no trailing punctuation, no acronyms, consistent grammar
      across the set (all nouns or all imperatives).

## 4. Banned strings

```bash
grep -nEi "\bwill\b|\bsimply\b|\bjust \b|\bvery\b|\beasily\b|\binstantly\b|of course|obviously|currently|\bsoon\b|latest|best |easiest|simplest|lightning-fast|not [a-z]+,? it.s|isn.t just|\be\.g\.|\bi\.e\.|tl;dr|\(s\)|delve|seamless|robust|comprehensive|unlock|empower|elevate|leverag|streamlin|designed to help you|designed for|whether you.re a" TARGET
```

- [ ] No "will" (use present tense instead).
- [ ] No "simply", "just", "very", "easily", "instantly", "of course", "obviously".
- [ ] No "currently", "soon", "latest", "new" — write timeless.
- [ ] No superlatives outside established brand phrasing on a homepage.
- [ ] No "e.g." or "i.e." — spell them out ("for example", "that is").
- [ ] No "(s)" plurals, no spelled-digit ordinals ("1st").
- [ ] No em dash with spaces around it; prefer splitting the sentence.
- [ ] No "It's not X, it's Y", no decorative rule-of-three, no LLM register.
- [ ] Exclamation points: zero in technical copy, at most one per conversion block.

## 5. Instructions

- [ ] **One action per step.** An "and" in a step means it's two steps.
- [ ] **Condition before action**, so a reader can skip what doesn't apply.
- [ ] **Verb matches the control**: *choose* from a menu, *select* or *clear* a checkbox,
      *click* or *tap* a button, *follow* or *open* a link, *enter* text in a field.
- [ ] **UI labels bolded**; anything typed verbatim in backticks.
- [ ] **Nothing obvious documented.** "Log in to your account" is filler unless the article
      is about logging in.
- [ ] **Positive framing**: what the reader can do, not what they can't.

## 6. Page furniture

- [ ] Two- or three-sentence intro so the reader can confirm they're in the right place.
- [ ] Tables hold data, not layout.
- [ ] The page ends by pointing somewhere useful — a related article, template, or support.
- [ ] `meta_description` (when applicable) is 150–160 characters and names the audiences.
- [ ] `page_title` (when applicable) is plain and matches what a reader would search for.

## 7. Ship

- [ ] Read it as a busy user who has never seen the product before. Can they act, or decide,
      after the first paragraph? If not, the first paragraph is doing something other than
      its job.

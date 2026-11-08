# Where these rules come from

This technical voice is synthesized from four published authorities rather than from
AI-generated or ad-hoc site content. This file records what each authority contributes and
how conflicts between them were resolved.

## The sources

**Google developer documentation style guide** — <https://developers.google.com/style>
The strictest of the four on person, tense, and claims. Machine-readable as the Vale
`Google` package (<https://github.com/errata-ai/Google>), which is what these rules were
read from; each rule there links back to the guide section it encodes.

**Microsoft Writing Style Guide** — <https://learn.microsoft.com/en-us/style-guide/welcome/>
Warmer than Google's, and the better source on word choice, sentence length, and describing
UI interactions. Also machine-readable, as the Vale `Microsoft` package
(<https://github.com/errata-ai/Microsoft>).

**18F Content Guide** — <https://content-guide.18f.gov/>
The best source on voice-versus-tone as a working distinction, on writing instructions, and
on positive framing. Explicitly permits contractions in an otherwise official register.

**Diátaxis** — <https://diataxis.fr/>
Not a style guide but a structural framework: four documentation types (tutorial, how-to
guide, reference, explanation) and a compass for deciding which one a page is. Adopted
because most documentation failures are a page trying to be two types at once.

## What each rule traces to

| Rule | Source |
|---|---|
| Second person; avoid first person and "we" | Google (`FirstPerson`, `We`), Microsoft (`We`), 18F |
| Present tense; cut "will" | Google (`Will`) |
| Active voice; "by zombies" test | 18F, Google (`Passive`), Microsoft (`Passive`) |
| Use contractions | All three style guides — Google (`Contractions`), Microsoft (`Contractions`), 18F |
| Sentences under 30 words | Microsoft (`SentenceLength`) |
| Everyday words over formal ones | Microsoft (`Wordiness`, `Jargon`) |
| "For example" not "e.g." | Google (`Latin`), Microsoft (`Foreign`) |
| No exclamation points in technical text | Google (`Exclamation`, error level); Microsoft (`ExclamationPoints`, "sparingly") |
| Questions sparingly | Microsoft (`QuestionMarks`) |
| No unverifiable claims (best, simplest) | Google (`ExcessiveClaims`) |
| Timeless phrasing — no "currently", "soon", "latest" | Google (`Timeless`) |
| No anthropomorphism | Google (`Anthropomorphism`) |
| No internet slang (tl;dr, IMO) | Google (`Slang`) |
| Sentence case headings, no acronyms in headings | Google (`Headings`), Microsoft (`Headings`, `HeadingAcronyms`) |
| Em dashes unspaced | Google (`EmDash`), Microsoft (`Dashes`) — both error level |
| Parentheses, semicolons, ellipses sparingly | Google (`Parens`, `Semicolons`, `Ellipses`) |
| Spell out ordinals; no "(s)" plurals | Google (`Ordinal`, `OptionalPlurals`), Microsoft (`Plurals`) |
| Name UI labels exactly, in bold | 18F, Microsoft |
| Verb matched to control (choose/select/click/follow) | 18F |
| Condition before action; one action per step | 18F |
| Positive framing ("Sign in to continue") | 18F |
| Two- or three-sentence intro | 18F |
| Tables only for data | 18F |
| Voice constant, tone variable | 18F |
| Four documentation types; the compass | Diátaxis |
| How-to guides: goal-named, action only, adaptable | Diátaxis |

## Conflicts, and how they were resolved

**Exclamation points.** Google forbids them outright; Microsoft allows them sparingly;
hand-written landing pages sometimes use them ("Start now!"). *Resolved:* banned in the
technical register, allowed one per block in the conversion register. This is the main
reason the skill splits registers at all.

**"Click" versus "select".** Microsoft standardizes on "select" for every input method. 18F
keeps a granular set: choose from menus, select checkboxes, click or tap buttons, follow
links. *Resolved:* 18F's set. It is more precise for web and desktop interfaces where
distinguishing menus, checkboxes, and buttons helps the reader scan.

**Superlatives.** Google's `ExcessiveClaims` flags "best" and "simplest". *Resolved:*
established brand taglines survive in the conversion register; documentation and comparison
copy make no superlative claims. A compare page argues from sourced facts, not from
adjectives.

**Contractions.** All three style guides *prefer* contractions, including for reference
material. Uncontracted technical prose ("When you are satisfied, click Save") is not more
authoritative — it just reads stiff.

**First-person plural.** Google and Microsoft both flag "we" and "let's". 18F's own voice
uses "we" freely, but 18F is writing *as* an organization about itself. *Resolved:* the
product or system is the subject in product copy; "we" is reserved for an About page, where
the team or company is genuinely the topic.

## Running this automatically with Vale

Both Google's and Microsoft's guides ship as Vale packages, so most of the mechanical rules
above are enforceable in CI rather than by review:

```ini
# .vale.ini
StylesPath = .vale/styles
MinAlertLevel = warning
Packages = Google, Microsoft

[docs/**/*.md]
BasedOnStyles = Google, Microsoft
```

Then run `vale sync && vale docs/`. Expect to disable a few rules that fight your domain
vocabulary — `Google.WordList` and `Microsoft.Terms` carry vendor-specific swaps, and
`Microsoft.GeneralURL` objects to "URL". The judgement-dependent rules in `SKILL.md`
(positioning, Diátaxis mode, whether a claim is verifiable) stay human.

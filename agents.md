# Agent Skills

Custom agent skills for AI-assisted development. These skills extend agent
capabilities with specialized behaviors that persist across conversations.

## Available skills

### humanizer

**Version:** 3.2.0
**License:** MIT
**Path:** `.agents/skills/humanizer/SKILL.md`

Remove the signs of AI-generated writing and produce text in a genuine human
voice. Applies to what the agent writes: chat replies, code comments, commit
messages, documentation, and prose. It is register-aware — rather than pushing
everything toward one "natural" style, it calibrates its rules to the kind of
writing in front of it, and it protects meaning (claims, citations, numbers,
hedges) from being changed while it edits.

Based on Wikipedia's "Signs of AI writing" guide, maintained by WikiProject AI
Cleanup. Field-specific voice profiles are grounded separately in real
peer-reviewed papers, cited within each profile.

#### What it covers

- **34 named patterns** across five categories: content; language and grammar;
  style; communication; and filler and hedging.
- **Register calibration** — classifies the text as academic/research,
  technical, teaching, or personal/editorial and applies each rule accordingly,
  then locks the register across the document (or per section in a long one) so
  the voice does not drift.
- **Protected content** — never silently alters claim strength, citations,
  quotations, numbers and units, defined terms, or reference lists, tables, and
  notation; flags an entangled pattern instead of rewriting through it.
- **Meaning-fidelity audit** — re-checks its own output for altered claims,
  dropped citations, changed numbers, and over-editing that flattens real voice.
- **Authoring vs. assessment** — when reviewing a student's work for a grade, it
  annotates the tells and hands the revision back rather than ghostwriting a fix.
- **Reusable voice profiles** — matches a specific author or field voice from a
  writing sample or a saved profile, loaded on demand.
- **Regression fixtures** — a self-test set that guards against reintroducing old
  mistakes when the skill changes.

#### Pattern categories

| Category | Patterns | Examples |
|---|---|---|
| Content | 1–6 | Inflated significance, promotional language, vague attributions |
| Language and grammar | 7–13 | AI-vocabulary words, copula avoidance, synonym cycling |
| Style | 14–19 | Em-dash handling, boldface overuse, title case in headings |
| Communication | 20–22 | Sycophantic tone, knowledge-cutoff disclaimers |
| Filler and hedging | 23–34 | Filler phrases, excessive hedging, manufactured punchlines, transition clustering |

#### Grounding

The core pattern catalog comes from Wikipedia's "Signs of AI writing"
(WikiProject AI Cleanup), built from observations of many instances of
AI-generated text. Field-specific voice profiles are grounded separately in real
published papers, with the sources cited inside each profile so the guidance is
traceable rather than improvised. An example profile for physical education,
sports science, and health research is included.

#### What it deliberately does not do

This skill is built to make writing read as genuinely human and well-made. It is
not built to defeat AI detectors, and using it that way misunderstands the tool.

- It does not optimize for detector scores. Lowering a perplexity-based
  detector's score reliably means making prose more generic and templated, which
  is the opposite of the goal.
- It accounts for detector bias. AI detectors misflag fluent non-native English
  as machine-written (Liang et al., 2023), so the skill treats non-native
  phrasing as neither a tell to flag nor something to "correct."
- It does not strip clean formatting to a fingerprint-free husk. Curly quotes,
  em dashes, and tidy structure are ordinary human output and count only when
  they cluster with other tells.

#### Usage

Once installed in `.agents/skills/`, the skill applies to the agent's text
output. Trigger an explicit pass in plain language:

```
Humanize this text.
```

For voice matching, provide a sample:

```
Humanize this text. Here's a sample of my writing for voice matching: [sample]
```

Or reference a file or saved profile:

```
Humanize this text. Use my writing style from [file path] as a reference.
```

When reviewing writing that is being graded, ask it to annotate rather than
rewrite, and it will name the patterns and leave the revision to the writer.

#### Installation

Clone this repo and the skill is available at `.agents/skills/humanizer/`. No
scripts or dependencies are required; the skill is instruction-only.

## Directory structure

```
.agents/
  skills/
    humanizer/
      SKILL.md     # Full skill instructions (34 patterns, register-aware)
      profiles/    # Optional field/author voice profiles
  agents.md        # This file
```

# Agent Skills

Custom agent skills for AI-assisted development. These skills extend agent
capabilities with specialized behaviors that persist across conversations.

## Available skills

### humanize

**Version:** 5.0.0
**License:** MIT
**Path:** `.agents/skills/humanize/SKILL.md`

Remove signs of AI-generated writing from all text output. Applies to
everything the agent produces: chat replies, code comments, commit messages,
documentation, prose, and technical writing.

Based on Wikipedia's "Signs of AI writing" guide plus research from Turnitin,
GPTZero, Originality.ai, Grammarly, Scribbr, and peer-reviewed academic
papers on AI text detection.

#### What it covers

- **42 named patterns** across six categories: content patterns, language and
  grammar patterns, style patterns, communication patterns, filler and hedging,
  and statistical patterns (AI detector triggers)
- **AI detector countermeasures** with specific notes for Turnitin, GPTZero,
  and Originality.ai
- **Anti-detection writing habits** countering five specific GPTZero feedback
  categories (task-oriented, robotic formality, mechanical precision, rigid
  guidance, lacks creative grammar)
- **Research-backed evasion principles** distilled from 7 peer-reviewed papers
  published at NeurIPS, ICML, and ICLR

#### Pattern categories

| Category | Patterns | Examples |
|---|---|---|
| Content | 1-6 | Inflated symbolism, promotional language, vague attributions |
| Language and grammar | 7-13 | AI vocabulary words, copula avoidance, synonym cycling |
| Style | 14-19 | Em dash overuse, boldface overuse, title case in headings |
| Communication | 20-22 | Sycophantic tone, knowledge-cutoff disclaimers |
| Filler and hedging | 23-33 | Filler phrases, excessive hedging, manufactured punchlines |
| Statistical (detector triggers) | 34-42 | Low perplexity, low burstiness, redundancy |

#### Peer-reviewed research integrated

1. Sadasivan et al. (2023) - "Can AI-Generated Text be Reliably Detected?" (ICLR 2024)
2. Krishna et al. (2023) - DIPPER paraphraser (NeurIPS 2023)
3. Zhang et al. (2024) - "Watermarks in the Sand" (ICML 2024)
4. Lu et al. (2023) - SICO framework
5. AuthorMist (2025) - RL-based detection evasion
6. Mitchell et al. (2023) - DetectGPT (ICML 2023)
7. Kirchenbauer et al. (2023) - LLM watermarking (ICML 2023)

#### Usage

The skill activates automatically when installed in the `.agents/skills/`
directory. Any agent that reads the skill file will apply the patterns to all
text it produces.

For voice matching, provide a writing sample:

```
Humanize this text. Here's a sample of my writing for voice matching: [sample]
```

Or reference a file:

```
Humanize this text. Use my writing style from [file path] as a reference.
```

#### Installation

Clone this repo and the skill will be available at `.agents/skills/humanize/`.
No scripts or dependencies required. The skill is instruction-only.

## Directory structure

```
.agents/
  skills/
    humanize/
      SKILL.md     # Full skill instructions (42 patterns + countermeasures)
  agents.md        # This file
```

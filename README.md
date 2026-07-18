# **Humanizer**

A Claude Agent Skill that removes the signs of AI-generated writing and helps produce text in a genuine human voice. It is register-aware: instead of pushing every document toward one "natural" style, it calibrates its rules to the kind of writing in front of it, and it protects meaning — claims, citations, numbers, hedges — from being changed while it edits.
Based on Wikipedia's Signs of AI writing, maintained by WikiProject AI Cleanup.

## What it does

Detects and rewrites a catalog of 34 documented AI-writing patterns: inflated significance, promotional language, superficial "-ing" analyses, vague attributions, em-dash overuse, rule-of-three padding, overused AI-vocabulary words, negative parallelisms, filler phrases, reflexive recaps, and more.
Runs in two modes. Rewrite mode cleans up existing text. Always-on mode applies the same standards to new writing as it is produced, rather than as an afterthought.


## How it works

The skill is more than a list of banned phrases. Its design is what keeps it from doing damage.

Register calibration, first. Every run starts by classifying the text as academic/research, technical, teaching, or personal/editorial, then applies each rule accordingly. A methods section is allowed to hedge and use passive voice; a lesson handout stays warm and plain; only personal/editorial writing gets the full voice-and-personality treatment. The register is locked for the document (or per section in a long one) so the voice does not drift.
Protected content. It never silently alters a claim's strength, a citation, a quotation, a number or unit, a defined term, or reference lists, tables, and notation. When an AI pattern is entangled with protected content, it flags the tension instead of rewriting through it.
Meaning-fidelity audit. After editing, it re-checks its own output for altered claim strength, dropped citations, and changed numbers — and for over-editing that flattens genuine voice.
Authoring vs. assessment. When the text is a student's work being evaluated, it switches to annotation — naming the tells and handing the improvement back — rather than ghostwriting a finished rewrite.
Reusable voice profiles. You can point it at a writing sample or a saved profile so it matches a specific author or field voice, loaded on demand.
Regression fixtures. A small self-test set guards against reintroducing old mistakes when the skill is changed.


## Installation

Install it as a Claude Agent Skill by placing the humanizer/ folder (containing SKILL.md) in your Claude environment's skills directory. For Claude Code this is commonly ~/.claude/skills/; adjust to your setup. Once installed, the skill activates on its own when you ask Claude to humanize or clean up text. you can also download the skill file and drag-drop it into Claude interface.

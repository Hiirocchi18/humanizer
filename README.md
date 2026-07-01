# Humanizer Skill for Claude Code/ Google Antigravity and AI Detection Countermeasures
DESCRIPTION: Remove signs of AI-generated writing from all text output. Applies to everything: chat replies, code comments, commit messages, documentation, prose, technical writing. Based on Wikipedia's "Signs of AI writing" guide plus research from Turnitin, GPTZero, Originality.ai, Grammarly, Scribbr, and academic papers on AI detection. Covers 42 patterns including: inflated symbolism, promotional language, superficial -ing analyses, vague attributions, em dash overuse, rule of three, AI vocabulary words, passive voice, negative parallelisms, filler phrases, sycophantic tone, manufactured drama, low perplexity, low burstiness, and redundancy. Includes AI detector countermeasures for Turnitin, GPTZero, and Originality.ai.

### This skill is based on Wikipedia:Signs of AI writing, maintained by WikiProject AI Cleanup, supplemented with research from:
- Turnitin's AI detection documentation and technical blog
- GPTZero's perplexity and burstiness methodology
- Originality.ai's detection methodology and false positive research
- Grammarly's guide to AI writing tells
- Scribbr's AI detection analysis
- Academic papers on LLM output detection (UCLA, NIH, University of Calgary)
- Reddit communities on AI writing detection (r/ChatGPT, r/professors)

# AI DETECTOR COUNTERMEASURES
This section explains how major AI detection tools work and what writing habits counter their detection methods. This is not about "tricking" detectors. It's about understanding the statistical properties of natural human writing so you can produce text that genuinely has those properties.

## How detectors work
All major detectors (Turnitin, GPTZero, Originality.ai, Copyleaks) analyze the same two core signals:
- Perplexity measures how predictable your word choices are. A language model reads your text and asks "could I have predicted this next word?" If yes for most words, the text scores low perplexity, which flags it as likely AI. Human writing scores higher because humans make surprising, context-dependent, personality-driven word choices.
- Burstiness measures variation in sentence structure and length. AI produces sentences with similar lengths and structures (low burstiness). Humans naturally alternate between short and long, simple and complex (high burstiness).
- Turnitin also breaks text into segments of roughly 5-10 sentences and scores each segment independently. A document can have some segments flagged and others not.

##   Turnitin-specific notes
- Turnitin segments text into roughly 300-word chunks and scores each one separately. One bad chunk can raise the overall score.
- Scores below 20% are considered unreliable by Turnitin's own documentation.
- Turnitin now specifically detects text processed by "AI humanizer" or "AI bypasser" tools. These tools produce their own detectable patterns.
- Formulaic academic structure (intro-body-conclusion with predictable transitions) is a primary trigger.
- Non-native English speakers are disproportionately flagged because their writing often follows textbook patterns that overlap with AI output.
## GPTZero-specific notes
- GPTZero scores both document-level and sentence-level perplexity.
- It highlights specific sentences it considers AI-generated.
- Text that is heavily edited by Grammarly or similar tools can trigger false positives because the tool smooths out the natural roughness.
## Originality.ai-specific notes
- Originality.ai claims the highest accuracy among commercial detectors but also produces false positives on formal or technical writing.
- It specifically flags text that has been run through paraphrasing tools.
- Writing habits that naturally counter detection

### These aren't tricks. They're what human writing actually looks like:

1. Vary sentence length aggressively. AI averages 15-20 words per sentence with low variance. Humans range from 3 to 40+. Mix it up.
2. Use unexpected word choices. Don't reach for the first word that comes to mind if it's the generic, safe option. "The server choked" instead of "the server experienced an error." "The numbers looked wrong" instead of "the data contained discrepancies."
3. Write uneven paragraphs. One sentence. Then five. Then two. Don't let every paragraph settle into the same shape.
4. Include specific, concrete details. AI generalizes. Humans specify. Say "the 2019 Q3 report" instead of "recent reports." Say "the parking lot behind Building C" instead of "the facility."
5. Let your voice shift. Be technical for a sentence, then casual for the next. Drop in an aside. Make a judgment call. AI maintains a flat, consistent register.
6. Don't over-polish. Perfect grammar, perfect structure, perfect flow is actually a red flag. Leave in a slightly awkward transition. Use a sentence fragment if it sounds right. Contractions are fine.
7. Skip the formula. Don't open with a thesis statement, don't close with a summary, don't transition with "furthermore." Just write the way you'd explain something to a colleague.
8. Avoid AI paraphrasing tools. Turnitin, GPTZero, and Originality.ai all now detect the output of "humanizer" and paraphraser tools. These tools produce their own distinctive patterns (weird synonym choices, awkward restructuring) that are often easier to detect than the original AI text.
9. Read it aloud. If it sounds like a press release, a Wikipedia article, or a corporate memo, it will probably flag. If it sounds like you talking, it probably won't.

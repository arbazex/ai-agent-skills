# ai-text-humanizer

**Detect and rewrite AI writing patterns. Makes text sound like a human wrote it.**

> Catches em dashes, forced three-item lists, sycophantic openers, hollow buzzwords ("delve," "landscape," "leverage," "robust"), structural tells, and 40+ other patterns — then rewrites them using the agent's own language capability. No API. No external calls. Just clean prose.

---

## What this skill does

AI-generated writing has fingerprints. Some are words ("delve," "utilize," "tapestry"). Some are phrases ("It's worth noting that," "At its core," "In today's fast-paced world"). Some are structural habits — the forced three-item list, the em-dash parenthetical, the "Certainly!" opener, the five-paragraph essay disguised as a blog post.

This skill gives an AI agent a master list of **45 documented tells**, each paired with a specific rewrite rule. When you hand it AI-generated text (or text that has been heavily edited with AI tools), it reads the piece, flags every pattern it finds, applies the rules, and returns prose that sounds like a person sat down and wrote it.

It is built on research. The patterns listed in SKILL.md are drawn from:
- Academic studies tracking vocabulary shifts in scientific papers post-ChatGPT (Juzek & Ward, Florida State University; Yakura et al., Max-Planck Institute)
- GPTZero's vocabulary frequency analysis comparing AI vs. human corpora
- The Reuters Institute for the Study of Journalism's analysis of AI prose divergence from human writing
- Wikipedia's community-assembled field guide to AI writing indicators
- Practitioner work from editors, moderators, and detection tool developers who have catalogued structural patterns at scale

---

## The 45 patterns covered

### Category A — Vocabulary tells (single words and short phrases)
| Code | Pattern | Rewrite direction |
|------|---------|------------------|
| A1 | "Delve" / "delve into" | Name the actual action |
| A2 | "Landscape" (metaphorical) | Name the actual domain |
| A3 | "Navigate" (metaphorical) | Use the concrete verb |
| A4 | "Tapestry" | Say what the thing actually is |
| A5 | "Nuanced" / "nuance" (filler) | Make the nuance explicit or cut |
| A6 | "Underscore" (verb) | "Show," "confirm," "make clear" |
| A7 | "Leverage" (verb) | "Use," "apply," "draw on" |
| A8 | "Robust" | Name the specific quality |
| A9 | "Seamless" / "seamlessly" | Describe what happens without friction |
| A10 | "Harness" (verb) | "Use," "channel," "put to work" |
| A11 | "Foster" (verb) | Be specific about how |
| A12 | "Utilize" | "Use" |
| A13 | "Comprehensive" (filler) | State the actual scope |
| A14 | "Pivotal" | Show why it matters |
| A15 | "Commendable" | State the praise directly |
| A16 | "Resonate" (metaphorical) | Name the actual reaction |
| A17 | "Streamline" | Name what is removed |
| A18 | "Empower" | "Let," "allow," "give X the ability to" |
| A19 | "Crucial" / "vital" / "paramount" | Show the consequence |
| A20 | "Multifaceted" | Name the facets |
| A21 | Hype adjectives: "groundbreaking," "revolutionary," "unprecedented" | Delete; describe the change |
| A22 | "Cutting-edge" / "state-of-the-art" / "innovative" | Describe what is actually new |
| A23 | "Game-changer" / "game-changing" | Show the change |
| A24 | "Whilst" (non-British) | "While" |
| A25 | "Boast" (features) | Direct statement |
| A26 | "Meticulous" / "meticulously" | Describe the process |
| A27 | "Swift" (AI synonym for fast) | "Fast," "quick," or actual speed |
| A28 | "Intricate" | Describe the complexity |
| A29 | "Synergy" / "synergistic" | Name what combines and the result |
| A30 | "Paradigm" (loose usage) | "Model," "approach," "way of thinking" |

### Category B — Phrase and sentence-level tells
| Code | Pattern | Rewrite direction |
|------|---------|------------------|
| B1 | "It's worth noting that" / "It's important to note that" | Cut and state the point |
| B2 | "At its core" / "At the heart of" | Delete; state the claim |
| B3 | "In today's fast-paced world" / "In today's digital age" | Cut; open with the actual claim |
| B4 | "In the realm of" / "In the world of" | Replace with "in" |
| B5 | "Shed light on" | "Explain," "clarify," "reveal" |
| B6 | "A testament to" | "Proof that," "evidence that" |
| B7 | "In conclusion" / "To summarize" / "In summary" | Cut the label; write the conclusion |
| B8 | "Let's dive in" / "Without further ado" | Cut; start |
| B9 | "Not only X but also Y" (repetitive) | Direct statement |
| B10 | "It's not X — it's Y" (em-dash contrast) | Choose one; state it cleanly |
| B11 | "Whether you're X or Y, Z" | Address the actual reader |
| B12 | "Maintains an active social media presence" | Say what they post or cut |
| B13 | "Plays a crucial role" | State the role |
| B14 | "Moving forward" (transition) | Cut |
| B15 | "When it comes to" | Cut and restructure |

### Category C — Structural and format tells
| Code | Pattern | Rewrite direction |
|------|---------|------------------|
| C1 | Em dash overuse (>1 per ~150 words) | Comma, period, colon, or "and" |
| C2 | Rule of three forced onto every list | Use the number of items that are accurate |
| C3 | Bullet-point addiction | Restore prose where items have narrative relationship |
| C4 | Five-paragraph essay template | Follow the argument's actual shape |
| C5 | Hyper-symmetrical paragraphs | Vary lengths deliberately |
| C6 | Filler transitions: "Furthermore," "Moreover," "Additionally" | Cut or use specific connector |
| C7 | Gerund fragment lists after a claim | Fold back into sentence |
| C8 | Sycophantic openers: "Great question!" | Cut; begin with the answer |
| C9 | Reflexive affirmations: "Certainly!" / "Absolutely!" | Cut; begin the response |
| C10 | Closing offer: "Let me know if you need anything else!" | Cut or make specific |
| C11 | Inline bold headers inside bullets | Prose or proper heading + paragraph |
| C12 | Announcing structure: "First… Second… Third…" | Perform the structure; don't announce it |
| C13 | Synonym cycling | Repeat the right word |
| C14 | Padding via restatement | Keep the clearest statement; add an example |
| C15 | Forced "both sides" balance | Take a position or give actual weighting |

---

## Usage

### Default mode — just fix it
Paste text and ask to rewrite, humanize, or de-AI it. The agent applies all matching rules silently and returns clean prose with a brief note on what was addressed.

### Detection report mode
Ask to "show me what's wrong first" before fixing. The agent returns a flagged list (pattern code + quoted phrase) followed by the rewrite.

### Audit mode
Ask to "annotate the original." The agent returns the original text with inline brackets marking each tell, then the clean version. Useful for learning which patterns to avoid going forward.

---

## What this skill does NOT do

- It does not call any external API or AI detection service.
- It does not change factual content — only style.
- It does not add hedges, qualifiers, or new filler while removing old filler.
- It does not refuse to process text on the grounds of topic sensitivity.
- It does not claim to make text "undetectable" by AI detection tools — that is a different (and ethically complicated) goal. This skill is about writing quality, not detection evasion.

---

## Design decisions

**Why a fixed list rather than an AI judgment call?**
A fixed list of named patterns with explicit rewrite rules is reproducible, auditable, and consistent. "Sound human" as a vague instruction produces inconsistent results. "Remove A1, A7, B2, and C1" produces consistent ones.

**Why no API?**
The agent's own language model is already capable of applying these transformations. Adding an external call introduces latency, cost, and a failure point for what is fundamentally a prose-editing task.

**Why 45 patterns?**
The list is drawn from documented, observed patterns in AI writing — not invented. Each entry has a clear behavioral source: it either appears in academic analysis, detection tool research, or systematic practitioner observation. No pattern was added as speculation.

---

## Research and sources

The patterns in this skill are grounded in:

1. **Juzek & Ward, Florida State University** — cross-referencing vocabulary spikes in scientific writing with ChatGPT overuse patterns; identified "focal words" whose increased prevalence correlates with AI usage ("delve," "commendable," "underscore").
2. **Yakura et al., Max-Planck Institute for Human Development** — documented spillover of ChatGPT vocabulary ("delve," "comprehend," "boast," "swift," "meticulous") into human speech in podcasts and academic talks after GPT's release.
3. **Reuters Institute for the Study of Journalism** — analysis of how AI prose diverges from human writing; documented consistent patterns in semi-formal and corporate vocabulary.
4. **GPTZero vocabulary analysis** — frequency comparison of AI vs. human corpora across millions of documents; identified words used 2× to 100× more often by AI.
5. **Wikipedia: Signs of AI Writing** — community-assembled field guide with real examples; documents em-dash overuse, rule-of-three, sycophantic openers, and structural templates.
6. **GitHub: AI Tropes (peteristhegreat)** — practitioner-assembled list of structural tells including synonym cycling, gerund fragment lists, padding via restatement, and the "It's not X — it's Y" em-dash pattern.
7. **Medium: The Em Dash Dilemma (Csutoras)** — practitioner investigation confirming em-dash overuse persists across prompting attempts, with analysis from OpenAI Community Forum threads.

---

## Installation

1. Copy the `SKILL.md` file into your agent's skills directory.
2. Rename the folder to `ai-text-humanizer` (lowercase, hyphens only, matching the `name` field).
3. Publish via your skill platform (ClawHub, OpenClaw, or equivalent).

No environment variables. No binaries. No setup beyond dropping the file.

---

## License

MIT. Use it, fork it, improve it. If you discover a new documented AI tell not in the list, open a PR with the source.

---

## Version history

| Version | Change |
|---------|--------|
| 1.0.0 | Initial release — 45 patterns across three categories |
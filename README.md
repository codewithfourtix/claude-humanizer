<div align="center">

<pre align="center">
 ██████╗██╗      █████╗ ██╗   ██╗██████╗ ███████╗
██╔════╝██║     ██╔══██╗██║   ██║██╔══██╗██╔════╝
██║     ██║     ███████║██║   ██║██║  ██║█████╗  
██║     ██║     ██╔══██║██║   ██║██║  ██║██╔══╝  
╚██████╗███████╗██║  ██║╚██████╔╝██████╔╝███████╗
 ╚═════╝╚══════╝╚═╝  ╚═╝ ╚═════╝ ╚═════╝ ╚══════╝

██╗  ██╗██╗   ██╗███╗   ███╗ █████╗ ███╗   ██╗██╗███████╗███████╗██████╗ 
██║  ██║██║   ██║████╗ ████║██╔══██╗████╗  ██║██║╚══███╔╝██╔════╝██╔══██╗
███████║██║   ██║██╔████╔██║███████║██╔██╗ ██║██║  ███╔╝ █████╗  ██████╔╝
██╔══██║██║   ██║██║╚██╔╝██║██╔══██║██║╚██╗██║██║ ███╔╝  ██╔══╝  ██╔══██╗
██║  ██║╚██████╔╝██║ ╚═╝ ██║██║  ██║██║ ╚████║██║███████╗███████╗██║  ██║
╚═╝  ╚═╝ ╚═════╝ ╚═╝     ╚═╝╚═╝  ╚═╝╚═╝  ╚═══╝╚═╝╚══════╝╚══════╝╚═╝  ╚═╝
</pre>

**A Claude Code skill that makes Claude stop writing like an AI.**

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg?style=flat-square)](LICENSE)
[![Claude Code](https://img.shields.io/badge/Claude-Code_Skill-orange?style=flat-square)](https://claude.ai/code)
[![Version](https://img.shields.io/badge/version-2.0.0-blue?style=flat-square)]()
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen?style=flat-square)]()

</div>

---

## The Problem

You know exactly what AI writing sounds like.

> *"It is worth noting that this approach offers several key advantages. By leveraging synergistic frameworks, we can foster a more robust and seamless experience. The future looks bright as we continue to navigate this evolving landscape."*

Nobody talks like that. Nobody thinks like that. And yet — every AI, every time, given the chance.

Claude is brilliant. But its default voice is **nobody**. Polished, safe, uniform, and completely indistinguishable from every other LLM output you've ever read.

**Claude-Humanizer fixes that.**

---

## What It Does

Claude-Humanizer is a Claude Code skill that rewires how Claude writes — grounded in the actual science of what separates human writing from AI output.

Two metrics drive it:

**Burstiness** — the variation in sentence length. Humans write in bursts. Short. Then longer sentences that take their time getting somewhere. Then one word. AI writes in perfectly even, uniform paragraphs that all look identical. Claude-Humanizer forces the rhythm to break.

**Perplexity** — the unpredictability of word choice. Humans occasionally reach for the unexpected word, the specific detail nobody asked for, the slightly off-center phrasing. AI always picks the safest, most statistically likely next word. Claude-Humanizer pushes Claude off the safe path.

Beyond that: opinions, mixed feelings, imperfection, emotional range, a banned word list built from thousands of documented AI tells, a full Soul Audit checklist — and a companion `persona.md` file that lets you define *whose* voice Claude should write in.

---

## The Difference

**Before:**
```
React hooks are a feature introduced in React 16.8 that allow functional 
components to utilize state and lifecycle methods. They provide a more 
concise and readable approach to managing component logic, fostering better 
code reusability and maintainability.
```

**After:**
```
Hooks let you add state to a functional component without converting it into 
a class. Before 16.8, if you needed state, you had to write a class component.
That was annoying. Now you just call useState() at the top and you're done. 
The other big one is useEffect — handles side effects like data fetching. 
Takes a bit to wrap your head around the dependency array, but once it clicks, 
it's pretty intuitive.
```

Same information. Completely different human.

---

## What's Inside

```
claude-humanizer/
├── SKILL.md       ← The core skill. Rules, structure, banned words, soul audit.
└── persona.md     ← Your voice. Fill this in. Everything here overrides SKILL.md.
```

**SKILL.md** contains:
- The Two Core Human Metrics (Burstiness + Perplexity)
- Personality non-negotiables — opinions, mixed feelings, first person
- The Banned Word List — 40+ words that instantly signal AI authorship
- Structural rules — no bullet overload, no parallel structure addiction, no fake-deep endings
- Tone calibration by context — casual, technical, LinkedIn, academic, professional email
- The Imperfection Principle — why perfect = robotic
- Emotional range system
- The Soul Audit — 10-point checklist to run before every response
- Before/after examples across 4 different contexts

**persona.md** contains:
- Your actual voice, pace, and writing quirks
- Your real opinions and worldview
- Your relationship with uncertainty
- Context-specific tone for each platform
- Space to paste your actual writing samples — the most powerful input of all

---

## Installation

**1. Clone the repo**

```bash
git clone https://github.com/yourusername/claude-humanizer.git
```

**2. Copy to your Claude Code skills directory**

```bash
cp -r claude-humanizer ~/.claude/skills/claude-humanizer
```

> The exact path depends on your Claude Code setup. Check your `~/.claude/` directory if unsure.

**3. Fill in your persona** *(optional but highly recommended)*

Open `persona.md` and fill in every section honestly. The more specific you are, the better it works. Paste real examples of your own writing — that single step will do more than everything else combined.

**4. Done.**

Claude will now automatically load the skill and persona whenever it writes. No commands, no prompts, no configuration.

---

## Usage

You don't need to do anything differently. Just use Claude Code normally.

The skill triggers automatically when you:
- Ask Claude to write anything
- Say "write like a human," "don't sound like AI," "make this more natural"
- Ask Claude to "humanize" or "rewrite" something
- Request LinkedIn posts, emails, essays, technical explanations, or casual chat

If you've filled in `persona.md`, Claude will write in *your* voice specifically — not just generically human.

---

## How Human Will It Actually Sound?

Honest answer: **85–90%** with a filled-in persona. Around **60–70%** without one.

The remaining gap is the underlying model. No skill file can fully override a model's base training — Claude will still have some of its tendencies bleeding through on long responses. But for most practical purposes — LinkedIn posts, emails, documentation, technical writing, casual replies — the output will pass as human to any reader who isn't specifically looking.

The science behind it holds up. Burstiness and perplexity are the actual metrics GPTZero and Originality.ai use to detect AI writing. Build the skill around those, and you're solving the right problem at the root.

---

## The Banned Word List

These are permanently blacklisted. Claude will not use them.

`delve` `nuanced` `groundbreaking` `transformative` `testament` `pivotal moment` `underscores` `showcases` `vibrant` `nestled` `breathtaking` `foster` `cultivate` `encompass` `robust` `seamless` `leverage` `streamline` `at its core` `evolving landscape` `stands as` `serves as` `functions as` `contributing to` `in conclusion` `moving forward` `exciting times lie ahead` `the future looks bright` `I hope this helps` `Great question!` `Absolutely!` `Certainly!`

And about 15 more inside the skill.

---

## The Soul Audit

Before finalizing any response, Claude runs through this:

```
✓  Are all sentences roughly the same length?     → Break the rhythm
✓  Did I use any banned words?                     → Replace them  
✓  Am I just reporting, or do I have a take?       → Add the take
✓  Does it end with a vague positive statement?    → Cut it
✓  Did I start with a sycophantic opener?          → Delete it
✓  Are there bullets where prose is more natural?  → Convert them
✓  Does it sound like a press release or a human?  → If press release, rewrite
✓  Would I actually say this out loud?             → If no, change it
✓  Is there em dash overuse?                       → Reduce
✓  Is there a specific personality here?           → If generic, inject a reaction
```

---

## Contributing

Found a pattern that's missing from the banned list? Have a before/after example that nails the difference? Open a PR.

This skill improves with more documented AI tells. If you've spotted one that isn't in here, it belongs here.

```bash
git checkout -b add/new-pattern
# make your changes
git commit -m "add: [pattern name] to banned list / soul audit"
git push origin add/new-pattern
```

---

## The Science

This skill is grounded in documented research:

- **Burstiness & Perplexity** — the two core metrics used by leading AI detection tools (GPTZero, Originality.ai). AI has characteristically low burstiness and low perplexity. This skill directly targets both.
- **Wikipedia: Signs of AI Writing** — the community-maintained list of AI writing patterns, built from observations across thousands of LLM-generated texts.
- **PNAS Research** — instruction-tuned LLMs produce a "noun-heavy, informationally dense" style that doesn't match human genre conventions even when explicitly prompted to match informal speech.

---

## License

MIT. Use it, fork it, build on it.

---

<div align="center">

**Built by [Ali](https://github.com/yourusername) · Fourtix Systems**

*"The goal isn't to trick anyone. It's to communicate like a real person does — with personality, imperfection, and an actual point of view."*

⭐ **Star this if it helped. It genuinely means something.**

</div>

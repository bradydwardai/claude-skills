# Claude Code Skills

10 production-grade [Claude Code](https://claude.com/claude-code) skills — drop-in, documented, and built to work outside any one person's setup. Not a scraped dump: every one of these has been in daily use since 2026-04-23 inside a real, gate-enforced autonomous dev pipeline (research → plan → build → verify → ship, no exceptions) — not written once and published.

A *skill* is a directory with a `SKILL.md` (YAML frontmatter + instructions) that Claude Code loads on demand when your request matches its `description`. Drop these into `.claude/skills/` and they activate automatically.

### explain-code, in one pass

```
$ (ask Claude Code: "explain this auth middleware to me")
→ Real-world analogy → ASCII diagram of the request flow → line-by-line
  walkthrough → gotchas ("this silently no-ops if the header casing is
  wrong") → suggested next read. No hand-holding, no fluff.
```

### pricing-strategy, in one pass

```
$ (ask Claude Code: "help me price my SaaS")
→ Segments the buyer, proposes 3 tiers with a named value metric,
  flags the freemium trap before you build it, and gives you the
  exact pricing-page copy to test.
```

## Skills

| Skill | What it does | Reach for it when… |
|-------|--------------|--------------------|
| **pricing-strategy** | Designs SaaS pricing, packaging, and monetization that captures value and aligns with willingness to pay. | "what should I charge", pricing tiers, freemium, free trial, price increase, value metric |
| **project-scaffold** | Scaffolds a brand-new full-stack app — Next.js 15 + TypeScript + Tailwind + shadcn/ui + Supabase + Vercel — step by step. | "start a new project", "scaffold an app", bootstrapping a full-stack project |
| **explain-code** | Explains code with a real-world analogy, a diagram, a line-by-line walkthrough, key concepts, gotchas, and how to modify it. | "explain this code", "walk me through this", onboarding to an unfamiliar codebase |
| **copy-editing** | Improves existing marketing/conversion copy through focused editing passes while preserving the core message. | "review my copy", "tighten this up", "proofread", "make this better" |
| **churn-prevention** | Designs cancel flows, dynamic save offers, and dunning/failed-payment recovery to cut both voluntary and involuntary churn. | "churn," "cancel flow," "save offer," "dunning," "people keep canceling" |
| **marketing-psychology** | Applies psychological principles and mental models — anchoring, social proof, scarcity, loss aversion — to marketing decisions. | "psychology," "cognitive bias," "why people buy," "persuasion" |
| **ai-seo** | Optimizes content to get cited by AI search engines and LLM-generated answers (AEO/GEO/LLMO). | "AI SEO," "AI Overviews," "optimize for ChatGPT/Perplexity," "AI citations" |
| **popup-cro** | Designs and optimizes popups, modals, overlays, and banners for conversion without annoying users. | "exit intent," "popup conversions," "modal optimization," "lead capture popup" |
| **programmatic-seo** | Builds SEO-driven pages at scale from templates and data, without tripping thin-content penalties. | "programmatic SEO," "pSEO," "location pages," "generate 100 pages" |
| **free-tool-strategy** | Plans and evaluates free tools (calculators, generators) as a lead-gen and SEO growth lever. | "engineering as marketing," "free tool," "lead gen tool," "ROI calculator" |

## Install

With the [`skills` CLI](https://skills.sh):

```bash
npx skills add bradywardai/claude-skills
```

Or copy any skill directory directly into your project's `.claude/skills/`:

```bash
git clone https://github.com/bradywardai/claude-skills
cp -r claude-skills/skills/pricing-strategy .claude/skills/
```

## How to use a skill

Once a skill is in `.claude/skills/`, Claude Code loads it automatically when your request matches its `description` — you don't invoke it manually. Just describe what you want ("help me price my SaaS", "explain this function", "reduce churn on my SaaS") and the matching skill activates.

## License

[MIT](./LICENSE). Free to use, copy, modify, and redistribute.

## About

Built by [Brady Ward](https://bradyward.ai/?utm_source=github&utm_medium=skills-repo&utm_campaign=flagship-skills), who teaches Claude Code workflows at [Claude Code 101](https://bradyward.ai).

## Attribution

These skills are original work. They are **not** affiliated with — and do not redistribute — the excellent third-party Claude Code skills you may also have installed, such as [caveman](https://github.com/JuliusBrussee/caveman), the [Obsidian skills](https://github.com/kepano/obsidian-skills), or [impeccable](https://github.com/pbakaus/impeccable). Install those from their own authors.

# Launch Packet

The load-bearing work isn't publishing — it's the **coordinated launch motion**. Everything below
is drafted and ready to fire.

---

## A. awesome-claude-code submission (the single highest-leverage action)
**Target:** [hesreallyhim/awesome-claude-code](https://github.com/hesreallyhim/awesome-claude-code)
(~46-50K★). **Corrected mechanic (their CONTRIBUTING.md, verified live):** PRs are **banned** for
resource recommendations — submissions go through the **GitHub Issues web-UI form**
(`recommend-resource.yml`) and must be submitted by a human maintainer, not `gh`-CLI or an agent.

Open `https://github.com/hesreallyhim/awesome-claude-code/issues/new?template=recommend-resource.yml`
and paste in the entry details below. Entry descriptions must be **single-line, factual
statements — no persuasive copy, no emoji**, per their current rules:

```markdown
- [pricing-strategy](https://github.com/bradydward/claude-skills/tree/main/skills/pricing-strategy) - Designs SaaS pricing, packaging, and monetization aligned with willingness to pay.
- [project-scaffold](https://github.com/bradydward/claude-skills/tree/main/skills/project-scaffold) - Scaffolds a full-stack Next.js 15 + Supabase + shadcn/ui app from scratch, step by step.
- [explain-code](https://github.com/bradydward/claude-skills/tree/main/skills/explain-code) - Explains code with analogies, diagrams, line-by-line walkthroughs, and gotchas.
- [copy-editing](https://github.com/bradydward/claude-skills/tree/main/skills/copy-editing) - Improves existing marketing copy through focused editing passes.
- [churn-prevention](https://github.com/bradydward/claude-skills/tree/main/skills/churn-prevention) - Designs cancel flows, save offers, and dunning to cut voluntary and involuntary churn.
- [marketing-psychology](https://github.com/bradydward/claude-skills/tree/main/skills/marketing-psychology) - Applies psychological principles and mental models to marketing decisions.
- [ai-seo](https://github.com/bradydward/claude-skills/tree/main/skills/ai-seo) - Optimizes content to get cited by AI search engines and LLM-generated answers.
- [popup-cro](https://github.com/bradydward/claude-skills/tree/main/skills/popup-cro) - Designs and optimizes popups, modals, and overlays for conversion.
- [programmatic-seo](https://github.com/bradydward/claude-skills/tree/main/skills/programmatic-seo) - Builds SEO-driven pages at scale from templates and data.
- [free-tool-strategy](https://github.com/bradydward/claude-skills/tree/main/skills/free-tool-strategy) - Plans and evaluates free tools as a lead-generation and SEO growth lever.
```

## B. Cross-registry launch posts (same day as the submission)

**Short post (X / dev community):**
```
Published 10 Claude Code skills, battle-tested in a real gate-enforced dev pipeline since
2026-04-23 — not written once and dumped:

• pricing-strategy — what to actually charge
• explain-code — code explained with analogies + diagrams
• churn-prevention — cancel flows + save offers that actually reduce churn
• ai-seo — get cited by ChatGPT/Perplexity, not just Google
• + 6 more

MIT, drop-in: npx skills add bradydward/claude-skills
```

**GitHub release note (v1.0.0):**
```markdown
# v1.0.0 — first public release

10 standalone Claude Code skills, MIT licensed, in daily production use since 2026-04-23:

- **pricing-strategy** — SaaS pricing, packaging, monetization
- **project-scaffold** — full-stack Next.js 15 + Supabase + shadcn/ui scaffold
- **explain-code** — beginner-friendly code explanations (analogy → diagram → walkthrough)
- **copy-editing** — focused editing passes on existing copy
- **churn-prevention** — cancel flows, save offers, dunning/failed-payment recovery
- **marketing-psychology** — psychological principles applied to marketing decisions
- **ai-seo** — optimize content to get cited by AI search engines
- **popup-cro** — popup/modal/overlay conversion optimization
- **programmatic-seo** — SEO pages at scale from templates and data
- **free-tool-strategy** — free tools as a lead-gen and SEO growth lever

Install: `npx skills add bradydward/claude-skills`, or copy any `skills/<name>/` into your
project's `.claude/skills/`.
```

## C. Demo / output samples
Two static output samples (pricing-strategy, explain-code) are embedded directly in the README —
scoped down from a full demo GIF (research found this is a real discovery lever, but a GIF wasn't
worth the extra production time for a first launch). A GIF remains a good future addition if the
static samples don't move the needle.

## D. Same-day sequence (run top to bottom)
1. Create the public GitHub repo + push the seed — from the seed dir: `git init`, commit, then `gh repo create bradydward/claude-skills --public --source=. --push`.
2. Set repo topics (`claude-code-skills`, `skills-sh`, `claude-code`, `ai-skills`, `agent-skills`, `agentic-ai`, `developer-tools`) → skills.sh becomes eligible for discovery.
3. Cut the v1.0.0 GitHub release (note from B).
4. Submit to ClawHub (accept MIT-0, login started early to clear the account-age gate) — see `REGISTRIES.md`. Agensi is a separate, later step (Stripe Connect signup required first).
5. Submit the awesome-claude-code issue-form (A) — this step cannot be automated per their rules, a human has to click submit.
6. Post the short post (B) linking the repo + (once merged) the awesome-list entry.

> Doing 1–4 in one session is what triggers GitHub's trending/recency signals — don't spread it over days. Step 5 depends on maintainer availability and isn't a same-day blocker for the rest.

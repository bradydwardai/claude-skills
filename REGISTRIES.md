# Registry Submission Guide

Copy-paste-ready submission steps per registry. Mechanics from research (2026-06-17, re-verified
2026-07-09). The repo seed lives in this directory (`skills/`, `README.md`, `LICENSE`). Submit
GitHub first — it's the source every other registry works from.

> **Universal minimum:** every `SKILL.md` needs YAML frontmatter with `name` + `description`. All 10 skills already satisfy this (name === folder, version 1.0.0), and each carries a named "use when..." trigger phrase in its description — the field registries actually index for discovery.

---

## 1. GitHub (do this first — it's the hub)
**Mechanic:** a public repo is the source every other registry indexes.
**Steps:**
1. Create the public repo and push the seed (exact commands in `LAUNCH.md` §D step 1).
2. Set repo **topics**: `claude-code-skills`, `skills-sh`, `claude-code`, `ai-skills`, `agent-skills`, `agentic-ai`, `developer-tools`.
3. Confirm `README.md` renders (per-skill table + one-command install) and `LICENSE` is detected by GitHub as MIT.
**Required fields:** repo name, description, topics. **Gotcha:** widen the topic list — a narrow tag set undersells the repo to GitHub's own topic-search.

## 2. skills.sh
**Mechanic:** documented convention (not independently re-verifiable this session — vercel-labs/skills'
own docs don't confirm automatic topic-tag indexing as fact). The **confirmed** discovery mechanism
is CLI install telemetry: `npx skills add <user>/claude-skills` registers the repo and drives its
install-count ranking.
**Steps:**
1. Set the `skills-sh` GitHub topic (step 1.2 above) — a documented, zero-cost convention worth doing regardless.
2. Run `npx skills add bradydward/claude-skills` yourself once to seed the install counter — this is the confirmed discovery lever, not the topic tag alone.
**Required fields:** `name` + `description` per skill (already present). **Gotcha:** ranking is install-count-driven and vendor-dominated — the launch motion (awesome-list submission + posts in `LAUNCH.md`) is what drives installs, not the listing itself.

## 3. ClawHub (manual CLI publish)
**Mechanic:** `clawhub login --device` (GitHub OAuth device flow) then `clawhub publish`. GitHub
account must clear ClawHub's minimum-age gate — start the login early (see plan Task 4) so the
clock runs in parallel with the rest of the launch, not after it. VirusTotal scan, no human
pre-review.
**Steps:**
1. `clawhub login --device` — drive the GitHub-OAuth authorize click via an already-signed-in browser session.
2. For each skill: `clawhub publish` from the skill directory (or per ClawHub's current repo-based flow), using the MIT-0 license variant (`LICENSE-CLAWHUB`).
**Required fields:** `name`, `version`, `tags`, `description`.
**🚩 Gotcha — license:** ClawHub **mandates MIT-0 at the platform level**. Our repo LICENSE is MIT (MIT-0-compatible upstream). Use the pre-generated `LICENSE-CLAWHUB` variant for this registry's copy — don't hand-edit or "accept" an override mid-CLI-session.

## 4. Agensi (manual ZIP upload + human review)
**Mechanic:** upload a skill ZIP at agensi.io/creators. 8-point security scan + human editorial
review. **Requires a Stripe Connect account link at signup, even for free skills** — a one-time
identity/financial-account creation step that only the account owner can complete.
**Steps:**
1. Create an Agensi creator account + link Stripe Connect (one-time, account owner only).
2. Zip each skill directory (the folder containing `SKILL.md` + any `references/`).
3. Upload at agensi.io/creators with a description that includes **trigger phrases** (already embedded in each skill's frontmatter).
**Required fields:** `name` (≤64 chars, **must match the folder name** — all 10 already do) + a description **with trigger phrases** (already present).
**🚩 Gotcha — near-dupes:** Agensi flags near-duplicate submissions. `pricing-strategy`/`copy-editing` have partial name overlap with a dominant incumbent repo (`coreyhaines31/marketingskills`) — the other 8, especially the 6 newest, were chosen specifically to avoid this. Don't also submit any of the excluded third-party (vendored) skills.

---

## Per-surface gotcha summary (don't trip on these)
| Surface | License | Index | Key requirement |
|---------|---------|-------|-----------------|
| GitHub | MIT (detected) | n/a (it's the source) | 7 topics set |
| skills.sh | inherits repo MIT | CLI install telemetry (`npx skills add`) | run the install command once |
| ClawHub | **MIT-0** (`LICENSE-CLAWHUB` variant) | manual CLI, device-flow OAuth | account-age gate — start login early |
| Agensi | inherits MIT | manual ZIP + review | account-owner-only signup (Stripe Connect), then scriptable |

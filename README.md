# Awesome Claude Skills - Part 2

Skills from `linkedin-skills` to `zero-hallucination-coder` (558 folders). Part 1 (a11y-audit to linkedin-profile, 557 folders) lives in https://github.com/Jahangirhussen/awesome-claude-skills-1000. Together they hold the full audited library (1,351 skills, 15 domains).

## One-click setup
Installs **both parts** (all 1,351 skills) and enables auto-routing. Needs only Git and Claude Code. It overwrites same-name skills in `~/.claude/skills` and appends two short rule blocks to `~/.claude/CLAUDE.md` (backup `CLAUDE.md.bak`; set `SKIP_RULES=1` to skip the rules).

macOS / Linux / Git Bash:
```bash
curl -fsSL https://raw.githubusercontent.com/Jahangirhussen/awesome-claude-skills-1000/main/install.sh | bash
```
Windows PowerShell:
```powershell
irm https://raw.githubusercontent.com/Jahangirhussen/awesome-claude-skills-1000/main/install.ps1 | iex
```
Then restart Claude Code. Read the script first if you like: [install.sh](install.sh), [install.ps1](install.ps1).

## What is in this repo
Library is split in two repos: Part 1 = [awesome-claude-skills-1000](https://github.com/Jahangirhussen/awesome-claude-skills-1000), Part 2 = [awesome-claude-skills-part2](https://github.com/Jahangirhussen/awesome-claude-skills-part2).
This repo: **Part 2 (awesome-claude-skills-part2)**, 558 skill folders (`linkedin-skills` to `zero-hallucination-coder`). Full per-skill list with score and source: [SKILLS-TABLE.md](SKILLS-TABLE.md).

Scores are /100 from a heuristic structure rubric (not human review). Sub category exists mainly for SEO; other domains are flat.

| Skill Category | Sub Category | Skills in this repo | Avg Score /100 | Skill files incl. nested |
|---|---|---:|---:|---:|
| 01-DEVELOPMENT | general | 51 | 83 | 51 |
| 02-BUSINESS-SYSTEMS | accounting | 4 | 88 | 4 |
| 02-BUSINESS-SYSTEMS | business-automation | 47 | 85 | 47 |
| 02-BUSINESS-SYSTEMS | crm | 6 | 87 | 6 |
| 02-BUSINESS-SYSTEMS | ecommerce | 4 | 80 | 4 |
| 02-BUSINESS-SYSTEMS | hr | 7 | 83 | 7 |
| 02-BUSINESS-SYSTEMS | saas | 7 | 83 | 7 |
| 02-BUSINESS-SYSTEMS | shopify | 1 | 85 | 1 |
| 02-BUSINESS-SYSTEMS | woocommerce | 6 | 82 | 6 |
| 02-BUSINESS-SYSTEMS | wordpress | 28 | 81 | 28 |
| 03-AI | general | 48 | 84 | 48 |
| 04-RESEARCH | general | 64 | 87 | 66 |
| 05-SEO | 33 parent categories | 1 | 90 | 179 |
| 05-SEO | general | 3 | 86 | 3 |
| 06-MARKETING | general | 26 | 85 | 26 |
| 07-DATA | general | 20 | 87 | 20 |
| 08-DEVOPS | general | 33 | 85 | 33 |
| 09-SECURITY | general | 31 | 85 | 31 |
| 10-TESTING | general | 36 | 83 | 37 |
| 11-DESIGN | general | 46 | 85 | 46 |
| 12-AUTOMATION | general | 9 | 85 | 9 |
| 13-PRODUCT | general | 22 | 83 | 23 |
| 14-DOCUMENTATION | general | 29 | 83 | 29 |
| 15-SUPPORT | general | 4 | 90 | 4 |
| 99-UNCLASSIFIED | general | 24 | 50 | 15 |
| Library index | domains 01-15 + imports | 1 | 85 | 60 |
| **Total** | | **558** | **83** | **790** |


## Setup (for anyone)

**Requirements:** [Claude Code](https://docs.claude.com/en/docs/claude-code) installed, Git. Nothing else is needed for the skills themselves.

### 1. Download both parts
The library is split across two repos so every folder shows on GitHub (limit 1000 items per folder).

macOS / Linux / Git Bash:
```bash
git clone https://github.com/Jahangirhussen/awesome-claude-skills-1000.git
git clone https://github.com/Jahangirhussen/awesome-claude-skills-part2.git
mkdir -p ~/.claude/skills
cp -R awesome-claude-skills-1000/skills/* ~/.claude/skills/
cp -R awesome-claude-skills-part2/skills/* ~/.claude/skills/
```

Windows PowerShell:
```powershell
git clone https://github.com/Jahangirhussen/awesome-claude-skills-1000.git
git clone https://github.com/Jahangirhussen/awesome-claude-skills-part2.git
New-Item -ItemType Directory -Force "$env:USERPROFILE\.claude\skills" | Out-Null
Copy-Item awesome-claude-skills-1000\skills\* "$env:USERPROFILE\.claude\skills" -Recurse -Force
Copy-Item awesome-claude-skills-part2\skills\* "$env:USERPROFILE\.claude\skills" -Recurse -Force
```
Want only a few skills? Copy just those folders (each folder is one skill with a `SKILL.md`).

### 2. Turn on automatic routing (recommended)
Skills work on their own, but for the "just describe the task" experience add this to `~/.claude/CLAUDE.md` (create the file if missing):

```markdown
## Orchestrator
On any meaningful task, invoke the `master-auto-orchestrator` skill first, silently. It picks the right skills from the library. For substantial software builds it runs `universal-development-planner` before coding. SEO goes to `seo-master`. Dashboards, KPIs, charts go to `erp-saas-analytics-visualization`.

## Writing quality
When writing documents, emails, essays or reports for the user, apply `human-writing-mode` and `originality-guard`, and build files via `docs-pdf-clean-output`. Never invent facts or citations.
```

### 3. Restart and check
Restart Claude Code, then ask: *"Build me a small POS system"* (planner + orchestrator should start), or *"Audit the SEO of my site"* (`seo-master`). Type `/skills` or ask Claude to list skills to confirm they loaded.

### Notes
- **Claude Desktop** does not read `~/.claude/skills`. Zip a skill folder and upload it under Settings > Capabilities > Skills.
- ~1,350 skills means a long skill list. If it feels heavy, copy only the domains you use (for example `seo-master`, `master-auto-orchestrator`, `universal-development-planner`).
- Some skills need extra tools or accounts (MCP servers, API keys, Ahrefs, Stripe). Read the skill's `SKILL.md`. Never commit your own keys.
- Skills are third-party and original mixed; check `CREDITS.md` for licenses before commercial reuse.
- Quality scores come from a heuristic rubric (average 84.5), not human review. Report problems via GitHub issues.

# Awesome Claude Skills - Part 2

All **agent skills** (agents, orchestration, MCP, memory, prompts, planning/execution workflows, skill authoring). Part 1 (SEO, development and everything else) lives in https://github.com/Jahangirhussen/awesome-claude-skills-1000. Together they hold the full audited library (1,351 skills, 15 domains).


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
This repo: **Part 2 (awesome-claude-skills-part2)**, 153 skill folders (agent skills: agents, orchestration, MCP, memory, prompts, planning/execution workflows, skill authoring). Full per-skill list with score and source: [SKILLS-TABLE.md](SKILLS-TABLE.md).

Scores are /100 from a heuristic structure rubric (not human review). Sub category exists mainly for SEO; other domains are flat.

| Skill Category | Sub Category | Skills in this repo | Avg Score /100 | Skill files incl. nested |
|---|---|---:|---:|---:|
| 01-DEVELOPMENT | general | 13 | 82 | 13 |
| 02-BUSINESS-SYSTEMS | business-automation | 13 | 84 | 13 |
| 02-BUSINESS-SYSTEMS | ecommerce | 1 | 82 | 1 |
| 02-BUSINESS-SYSTEMS | hr | 3 | 82 | 4 |
| 03-AI | general | 53 | 84 | 54 |
| 04-RESEARCH | general | 7 | 82 | 7 |
| 05-SEO | general | 1 | 84 | 1 |
| 06-MARKETING | general | 2 | 85 | 2 |
| 07-DATA | general | 1 | 82 | 1 |
| 08-DEVOPS | general | 9 | 87 | 9 |
| 09-SECURITY | general | 1 | 90 | 1 |
| 10-TESTING | general | 12 | 82 | 13 |
| 11-DESIGN | general | 8 | 81 | 8 |
| 12-AUTOMATION | general | 6 | 82 | 6 |
| 13-PRODUCT | general | 2 | 82 | 2 |
| 14-DOCUMENTATION | general | 6 | 86 | 7 |
| 15-SUPPORT | general | 4 | 82 | 4 |
| 99-UNCLASSIFIED | general | 11 | 81 | 12 |
| **Total** | | **153** | **83** | **158** |


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

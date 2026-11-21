# SPEC: CLAUDE.md / skills prompt audit

Source: Instagram reel by nocodealex (Dd15NcHvlNl). Instagram reel, so there was one reader only (Claude), and Gemini was not used. Any line marked WEB came from a web search, not from the video.

## 1 Goal
- SINGLE SOURCE (Claude): Remove outdated prompting habits from CLAUDE.md, skills and prompts so Opus 5.5 works better and costs less.

## 2 Tools
- WEB, verified: the command is `/claude-api prompt-audit`. It is part of Anthropic's official `claude-api` skill (github.com/anthropics/skills, skills/claude-api/shared/prompt-audit.md), comes bundled with Claude Code 2.1.2xx and later, and is already present on this Mac (2.1.326). Sources: Anthropic docs "Optimizing for cost and intelligence", Lance Martin (Anthropic) on X, flaviocopes.com.
- WEB: `/doctor prompt-audit` is an alias.

## 3 Steps
- SINGLE SOURCE (Claude) + WEB: In Claude Code, run `/claude-api prompt-audit [optional file or folder]`.
- WEB: It writes an audit report table and a proposed diff. It edits files only if asked to apply them.

## 4 Inputs and outputs
- In: CLAUDE.md, AGENTS.md, SKILL.md files, commands, agents, prompts in code. Out: a report and a diff.

## 5 Prerequisites
- Claude Code with the bundled claude-api skill (already present). Nothing to install.

## 6 Gotchas
- WEB: The audit can flag "NEVER ..." prohibition lists. John's safety rules (free-reader limits, approved-plugins and scan rules, sandbox rules) are policy that must stay. They may be reworded, but never removed.
- WEB: Skills in ~/.claude/plugins/cache get overwritten on update. Fixes to John's own plugins have to go through ~/Claude/approved-plugins as a pull request and pass the security scan.
- The reel's numbers (about 70 fixes, 9%, 2 points) are the creator's claims. Anthropic's docs report similar but different numbers.

## OPEN QUESTIONS
- None blocking. The reel's "guide" sent by DM was not collected. The official prompt-audit.md replaces it.

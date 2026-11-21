# Prompt audit: ~/.claude/CLAUDE.md (2026-11-16)

**Assumptions.** Scope: only `/Users/johnfarrell/.claude/CLAUDE.md` (named in the request). It is user-level configuration, so any edit to it affects every project. Target model: Claude Opus 5.5 (the model running this audit; the file is read by Claude Code). Nothing was imported or skipped.

**Inventory.** One instruction file, 39 lines, with six sections: About me, approved-plugins system (add-plugin flow, NOT REVIEWED recovery), free-reader, agent-team, haiku-helper.

**Summary.** The file is clean, and no edits are proposed. It has no pressure language (no CAPS "MUST/CRITICAL"), no "double-check" or "think step by step" rituals, and no retired-model workarounds. Its one "Never" rule (line 15) and its one "Don't" rule (lines 23-25) are real policy, each with a stated reason. The step-by-step plugin flow (lines 9-14) is a fragile, security-sensitive procedure, so keeping exact commands is correct (keep-list item 3). Every path it names exists: `~/Claude/approved-plugins/mac-setup/add-plugin.sh` and `setup.sh`, the `john-approved` marketplace, the `agent-team` skill and the `chore-helper` agent.

Counts: Group 1 (dated prompt text) 0 · Group 2 (brittle config) 0 fixes, 2 flags · Group 3 (tool descriptions) not applicable · Group 4 (request code) not applicable.

## Findings

| Location | Evidence | Pattern | Why | Confidence | Action |
|---|---|---|---|---|---|
| CLAUDE.md:22-25 | "Never send ... to the free-reader tool" | Group 2, coverage (not a conflict) | The rule names only free-reader. The free-mode (FreeLLMAPI) skill sends text to the same free models, but its own SKILL.md carries the same rule, so behavior is consistent today. | Low | flag. Optionally rename the heading to "free-reader and free-mode". |
| CLAUDE.md:18 | "it lasts one year, created 2026-11-12" | Group 2, time-sensitive content | This date is useful context (it tells Claude when the token expires), not cruft. It needs updating when the token is renewed. | Low | flag, no edit. |

## Proposed diff

_Empty. No high- or medium-confidence findings._

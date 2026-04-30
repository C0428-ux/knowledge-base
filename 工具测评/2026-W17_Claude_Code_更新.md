# Week 17 · April 20–24, 2026 - Claude Code Release Summary

**Release Version:** v2.1.114 → v2.1.119  
**Documentation Index:** [https://code.claude.com/docs/llms.txt](https://code.claude.com/docs/llms.txt)

---

## 🚀 Major New Features

### /ultrareview — Research Preview

Cloud-based automated code review that runs a fleet of bug-hunting agents against your branch or PR.

```bash
# Review current branch
> /ultrareview

# Review a specific PR
> /ultrareview 1234
```

**Use case:** Run before merging critical changes (auth, data migrations).

→ [Ultrareview guide](https://code.claude.com/docs/en/ultrareview)

---

### Session Recap CLI

Get a one-line recap of what happened while you were away—helpful for managing multiple Claude sessions.

```bash
> /recap
```

Toggle automatic recaps on/off via `/config`.

→ [Interactive mode: session recap](https://code.claude.com/docs/en/interactive-mode#session-recap)

---

### Custom Themes (v2.1.118)

Build and ship custom color themes. Each theme extends a base preset, overriding only the tokens you need.

```bash
> /theme
```

Themes are stored as JSON in `~/.claude/themes/` and can be distributed via plugins.

→ [Terminal config: create a custom theme](https://code.claude.com/docs/en/terminal-config#create-a-custom-theme)

---

### Claude Code on the Web — Redesign

New look matching the desktop app:
- Sessions sidebar
- Drag-and-drop layout
- Refreshed routines view
- Faster response times
- More reliable experience

→ [Claude Code on the web](https://code.claude.com/docs/en/claude-code-on-the-web)

---

## 📋 Other Improvements

### Editor & Interaction
| Feature | Details |
|---------|---------|
| **Vim visual mode** | Press `v` for character selection, `V` for line selection with visual feedback |
| **MCP tool hooks** | Hooks can now call MCP tools directly via `type: "mcp_tool"` without spawning a process |
| **`/usage` command** | Merged from `/cost` and `/stats` (old names still work as shortcuts) |

### Configuration & Settings
| Change | Details |
|--------|---------|
| **Persisted settings** | `/config` changes (theme, editor mode, verbose) now save to `~/.claude/settings.json` |
| **Settings precedence** | Follows project/local/policy hierarchy |

### Subagents
- **Forked subagents** now available on external builds with `CLAUDE_CODE_FORK_SUBAGENT=1` — inherits full conversation context instead of starting fresh

### Model Defaults
- **Effort level** for Pro and Max subscribers on Opus 4.6 and Sonnet 4.6 now defaults to `high` (was `medium`)

### Performance
| Area | Improvement |
|------|-------------|
| **Native builds** | macOS/Linux now use embedded `bfs` and `ugrep` instead of `Glob`/`Grep` tools for faster searches |
| **`/resume` speed** | Up to **67% faster** on large sessions; now offers to summarize stale sessions before re-reading |
| **Opus 4.7 context** | Sessions now compute against native 1M context window (fixes inflated `/context` percentages and premature autocompaction) |

### Integrations
- **`--from-pr` now accepts:** GitLab merge requests, Bitbucket pull requests, GitHub Enterprise PRs (in addition to github.com)
- **Auto mode:** Use `"$defaults"` in `autoMode.allow`, `soft_deny`, or `environment` to add rules alongside built-ins instead of replacing

### Plugin Development
```bash
claude plugin tag
```
Creates release git tags for plugins with version validation.

→ [Tag plugin releases](https://code.claude.com/docs/en/plugin-dependencies#tag-plugin-releases-for-version-resolution)

---

## 📚 Resources

- [Full changelog for v2.1.114–v2.1.119](https://code.claude.com/docs/en/changelog#2-1-114)
- [Week 16 · Apr 13–17](https://code.claude.com/docs/en/whats-new/2026-w16)

**原始链接:** https://code.claude.com/docs/en/whats-new/2026-w17

# human-release-notes — AI release notes & changelog generator (Spanish)

Turn git commits and diffs into clear, user-facing release notes in Spanish (es-419) with any AI assistant: Claude Code, Cursor, GitHub Copilot, Codex or ChatGPT.

A skill that turns commits, diffs, or technical change lists into end-user release notes. Works with any AI assistant.

Output has three sections: **New**, **Improved**, and **Fixed**. Purely internal changes (refactors, dependency bumps, tests, CI) are filtered out.

Output language: neutral Latin American Spanish (es-419). Input can be in any language.

## Install

`SKILL.md` is the only file the AI needs. It is plain Markdown with no tool-specific dependencies.

### Any AI chat

Paste the contents of `SKILL.md` as the system prompt, custom instructions, or first message.

### Coding agents and IDEs

Put `SKILL.md` where your tool reads project instructions:

| Tool                                          | Location                                                                       |
| --------------------------------------------- | ------------------------------------------------------------------------------ |
| Claude Code                                   | `~/.claude/skills/human-release-notes/SKILL.md` (or project `.claude/skills/`) |
| Codex, Gemini CLI, others reading `AGENTS.md` | Append contents to `AGENTS.md`                                                 |
| Cursor                                        | Copy into `.cursor/rules/human-release-notes.mdc`                              |
| GitHub Copilot                                | Append contents to `.github/copilot-instructions.md`                           |

Claude Code, command line:

```bash
mkdir -p ~/.claude/skills/human-release-notes
cp SKILL.md ~/.claude/skills/human-release-notes/
```

PowerShell:

```powershell
New-Item -ItemType Directory -Force "$HOME\.claude\skills\human-release-notes" | Out-Null
Copy-Item SKILL.md "$HOME\.claude\skills\human-release-notes\"
```

## Usage

Ask your AI for release notes and paste or point to the source:

```
Write release notes for users from these commits:
<git log --oneline v1.2.0..HEAD>
```

```
Release notes from this diff: <git diff v1.2.0..HEAD>
```

If the input is unclear, the skill asks up to three questions before writing.

## Example output

```
## New
- You can export your reports to CSV from the Reports screen.

## Improved
- Search results load faster on large accounts.

## Fixed
- Dates no longer show one day off for users in UTC-3.
```

## License

MIT. See [LICENSE](LICENSE).

---

Made by [PLAF Labs](https://github.com/plaf-labs) · Software, automation and web development for SMEs and
industrial companies · [plaf.agency](https://plaf.agency)

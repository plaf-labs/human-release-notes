# Contributing

Thanks for helping improve human-release-notes.

## Scope

The project is one skill: `SKILL.md`. Changes must keep it:

- **Tool-agnostic.** No instructions tied to a single AI product, IDE, or tool name. The skill must work when pasted into any AI assistant.
- **Self-contained.** All behavior lives in `SKILL.md`. Do not add scripts, dependencies, or required setup.
- **Written in English.** The skill is English. The output it produces is neutral Latin American Spanish (es-419), and that rule must stay.

Out of scope: output in other languages by default, regional Spanish (voseo, country-specific slang), and features that only work in one tool.

## Before you open a pull request

1. Open an issue first for anything beyond a typo or a clear bug fix.
2. Keep the diff small. One change per pull request.
3. Test the change: run the skill on at least two inputs (a commit list and a diff) and check that:
   - Internal-only changes (refactors, dependencies, tests, CI) are omitted.
   - Each remaining change appears under exactly one of **New**, **Improved**, or **Fixed**.
   - Output is es-419, plain language, one sentence per bullet.
   - Empty sections are omitted.
   - The skill asks for clarification when input is unclear, instead of guessing.
4. Update `README.md` if install or usage changes.

## Examples and test inputs

- Use invented product names and data. Never include real customer, company, or personal data.
- Do not commit secrets, tokens, or private repository content.

## Pull request description

Include:

- What changed and why.
- The test inputs you used and the output you got.
- Any rule in `SKILL.md` you changed, and the reason.

## Commit messages

- Short imperative subject line, under 72 characters. Example: `Clarify Fixed section rules`.
- Body optional, for context.

## License

By contributing, you agree that your contribution is licensed under the MIT License in [LICENSE](LICENSE).

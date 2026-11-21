---
name: human-release-notes
description: Turns commits, a diff, or a technical change list into end-user release notes in three sections: New, Improved, and Fixed. Filters out purely internal changes (refactors, dependencies). Use when the user asks for "release notes", "changelog for users", or "what's new" built from commits, diffs, or change lists.
---

# human-release-notes

## Input

Accept any of:
- Commit list (`git log` output, pasted messages).
- Diff (`git diff`, patch).
- Hand-written technical change list.

If the input is empty or does not show what changed for the user, ask for more context before writing.

## Steps

1. Read the full input.
2. Drop purely internal changes: refactors, dependency changes, internal renames, tests, CI, formatting, code cleanup, version bumps.
3. Rewrite each remaining change from the user's point of view: what they can do now, what looks different, what no longer fails. No function, file, module, or technical jargon names.
4. Assign each change to exactly one section:
   - **New**: functionality that did not exist before.
   - **Improved**: something that existed and now works better, faster, or clearer.
   - **Fixed**: a bug the user could notice that no longer happens.
5. If a change does not clearly fit a section, or it is unclear whether users can see it, ask before including it.

## Output format

Write the output in neutral Latin American Spanish.

```
## Nuevo
- ...

## Mejorado
- ...

## Corregido
- ...
```

- One bullet per change, one sentence, plain language.
- Omit empty sections.
- No version header or date unless the user asks for one.
- No closing or summary.

## Rules

- Output language: neutral Latin American Spanish (es-419), unless the user asks for another language. Avoid regional slang (voseo, "vos", "ustedes" forms specific to one country).
- Do not invent features or benefits that are not in the input.
- If a commit mixes a visible change with an internal one, include only the visible part.
- If unsure, ask before generating the final document. Ask at most three questions at a time.

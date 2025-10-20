## Purpose

These instructions help AI coding agents quickly understand and contribute to this repository. They focus only on facts discoverable in the workspace and concrete, small-scope changes an agent can safely make without additional human guidance.

## Repo snapshot (discoverable)
- Files at repository root: `index.html`, `README.md` (both currently empty).
- Git: repository present, default branch `main`.

## Big-picture: what this repo is
- Minimal static project / single-page site. No build scripts, package manifests, or tests present.
- Because there is no server or tooling discovered, treat changes as edits to static assets (HTML, docs, small JS/CSS if added).

## Quick actionable rules for the agent
- Prefer small, reversible edits. Example: add a meta tag, improve README content, or patch `index.html` markup.
- Do not add large frameworks, heavy dependency manifests (e.g., `package.json`) or new CI workflows unless the user asks explicitly.
- If you need to add tooling or tests, explain the minimal changes and ask for confirmation in the pull request description.

## File- and pattern-specific notes
- `index.html`: the single entry file. When changing markup, preserve UTF-8 encoding and avoid touching `.git/` internals.
  - Example safe edits: add <meta charset="utf-8">, add a title, or insert a small inline stylesheet.
- `README.md`: currently empty — safe place to add project description, run instructions, or developer notes.

## Environment & workflow notes
- The user works on Windows (PowerShell); when suggesting terminal commands, use PowerShell-compatible syntax and paths.
- Project paths may contain non-ASCII characters (e.g., `d:\алкаши\...`). Use UTF-8 and quote paths when necessary.
- No build/test commands were detected. If you add tooling, include reproducible PowerShell commands in the PR description.

## Editing, commit and PR guidance
- Keep changes small and atomic. Use clear commit messages describing intent (one-line summary + 1–2 line body when helpful).
- If a change is larger than 10–20 lines or adds new tooling, open a draft PR and request a human review before merging.

## Integration points & external dependencies
- No external APIs, services, or packages are referenced in the discovered files. If you add integrations, document them in `README.md`.

## When to ask the user
- Ask before adding any of the following: new package manifests, CI pipelines, external services, or large refactors.
- Ask if you need runtime credentials, secrets, or the intended hosting target (GitHub Pages, static host, etc.).

## Example suggestions (copyable)
- Add a charset meta and title to `index.html`:
  - Safe one-file edit: insert `<meta charset="utf-8">` and `<title>Your project title</title>` inside `<head>`.
- Populate `README.md` with a 3-line project summary and a note that it’s a static single-file site.

## Closing
If any section here is unclear or you want the agent to follow different rules (for example, scaffold a Node project or add CI), reply with a short instruction and the agent will re-run with that scope.

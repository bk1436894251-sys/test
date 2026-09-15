# Codex repository instructions

## Purpose

This repository is maintained through an auditable GitHub pull-request workflow.

## Required workflow

- Never make feature work directly on `main`.
- Before editing, inspect `git status` and preserve unrelated user changes.
- Use a short branch name such as `docs/update-guide`, `feat/add-page`, or `fix/login-error`.
- Keep each branch and pull request focused on one purpose.
- Review `git diff` and run relevant checks before committing.
- Do not commit passwords, API keys, access tokens, private keys, `.env` files, or personal data.
- Use clear commit messages following `type: summary`, for example `docs: improve setup guide`.
- Do not force-push, rewrite published history, merge, or delete remote branches unless the user explicitly asks.
- Do not push or open a pull request when the user only requested analysis or review.
- When the user asks to implement a change, finish the local change and verification. Ask before any consequential GitHub operation that is not already clearly included in the request.
- In the final response, report the branch, commit, checks run, and pull-request URL when available.

## Pull requests

- Target `main` unless the user specifies otherwise.
- Explain what changed, why it changed, and how it was verified.
- Keep the checklist in `.github/PULL_REQUEST_TEMPLATE.md` accurate.
- Treat a green automated check as supporting evidence, not a substitute for reviewing the diff.

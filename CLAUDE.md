# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project

Spendly is a personal expense tracker built with Flask and SQLite (Python's built-in `sqlite3`, no ORM). It is a step-by-step teaching project: the UI shell exists, and features are implemented in numbered "Steps" that are referenced in stub comments and placeholder routes. Currency in the copy is rupees (₹).

## Commands

```bash
python -m venv venv && source venv/bin/activate   # venv/ is gitignored
pip install -r requirements.txt
python app.py          # dev server with debug reload at http://localhost:5001 (not 5000)
pytest                 # pytest + pytest-flask are installed; no tests exist yet
pytest path/to/test_file.py::test_name   # run a single test
```

There is no linter, formatter, or build step configured.

## Architecture

- `app.py` — the single Flask app; all routes live here with no blueprints. Routes are split into two sections: implemented pages (landing, register, login, terms, privacy) that only render templates, and **placeholder routes** returning strings like `"Profile page — coming in Step 4"`. When implementing a step, replace the matching placeholder rather than adding a new route. Templates reference routes via `url_for('<function name>')`, so keep function names stable.
- `database/db.py` — empty stub for Step 1. Intended contents: `get_db()` (SQLite connection with `row_factory` and foreign keys enabled), `init_db()` (`CREATE TABLE IF NOT EXISTS` for all tables), `seed_db()` (sample dev data). The DB file `expense_tracker.db` is gitignored.
- `templates/` — Jinja templates; every page extends `base.html`, which owns the navbar, footer, Google Fonts (DM Serif Display / DM Sans), `static/css/style.css`, and `static/js/main.js`. Pages hook in through `{% block title %}`, `{% block head %}` (page-specific CSS, e.g. `landing.html` loads `static/css/landing.css`), `{% block content %}`, and `{% block scripts %}` (page-specific inline JS).
- `register.html` / `login.html` already POST to `/register` and `/login`, but those routes are GET-only so far — auth logic is still to be built.
- Frontend is vanilla JS only — no JS frameworks or libraries.

## Conventions

- Commit messages are prefixed by area, e.g. `landing: add youtube modal on see how it works click`.
- Changes are typically scoped tightly: when asked to modify one section or file, don't touch other parts of the page. New content pages (like `terms.html`, `privacy.html`) should match the existing site theme.
- `file.txt` and `file.md` in the repo root are the user's scratch notes (prompt drafts, transcripts), not application code.

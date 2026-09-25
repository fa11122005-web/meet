---
name: uv-python-starter
description: Scaffold a new Python project with uv (Astral's package manager) using the standard "backend" starter - uv init backend, run a Hello World main.py, then uv sync. Use this skill whenever the user wants to start, bootstrap, initialize, or set up a new Python project, backend, API, or script with uv, or mentions "uv init", "uv run", "uv sync", or "Python starter/boilerplate" - even if they don't say "skill" or name uv explicitly.
---

# uv Python Starter

Creates a fresh Python project named `backend` with uv and verifies it runs with a Hello World.

## Workflow

Run these commands in order:

```bash
uv init backend
cd backend
uv run main.py
uv sync
```

1. `uv init backend` - creates the `backend/` folder with `pyproject.toml`, `main.py`, `.python-version`, `README.md`, and `.gitignore`.
2. `cd backend` - move into the project.
3. `uv run main.py` - runs the Hello World; uv creates `.venv` automatically on first run.
4. `uv sync` - installs/locks dependencies, writes `uv.lock`, and syncs `.venv`.

## Hello World

`uv init` already generates a `main.py`. To use this skill's version instead, overwrite it:

```bash
cp <skill-path>/scripts/main.py main.py
```

Source: `scripts/main.py` (prints `Hello, World!` and the Python version).

## Notes

- Project name: if the user asks for a different folder name, replace `backend` in every command.
- Adding packages afterwards: `uv add <package>` (e.g. `uv add fastapi uvicorn`), then `uv sync`.
- If `uv` is missing, install it first: `curl -LsSf https://astral.sh/uv/install.sh | sh` (macOS/Linux) or `powershell -c "irm https://astral.sh/uv/install.ps1 | iex"` (Windows).
- Expected output of `uv run main.py`: `Hello, World!`

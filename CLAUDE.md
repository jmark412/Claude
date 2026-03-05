# CLAUDE.md — AI Assistant Guide for This Repository

## Repository Overview

This is the **jmark412/Claude** repository. It serves as a project workspace for Claude-assisted development.

## Project Structure

```
.
├── CLAUDE.md          # This file — guidance for AI assistants
└── (project files)    # Added as the project evolves
```

## Development Workflow

### Branch Conventions

- **Main branch**: `main` — stable, production-ready code
- **Feature branches**: Use `claude/<description>-<ID>` naming convention
- Always create pull requests for merging into `main`

### Commit Messages

- Use clear, descriptive commit messages
- Start with an imperative verb (e.g., "Add", "Fix", "Update", "Remove")
- Keep the subject line under 72 characters
- Add a blank line and body for complex changes

### Code Quality

- Write clean, readable code with meaningful variable and function names
- Follow the language-specific style conventions used in each file
- Avoid over-engineering — keep solutions simple and focused
- Do not add unnecessary comments; code should be self-documenting where possible

## Commands

### Git

```bash
git status                    # Check working tree status
git add <files>               # Stage specific files
git commit -m "message"       # Commit with message
git push -u origin <branch>   # Push and set upstream
```

## Conventions for AI Assistants

1. **Read before editing** — Always read a file before modifying it
2. **Minimal changes** — Only change what is necessary to accomplish the task
3. **No speculative features** — Don't add code "just in case"
4. **Respect existing patterns** — Follow the conventions already established in the codebase
5. **Test your work** — Run available tests/linters before committing
6. **Security first** — Never commit secrets, credentials, or sensitive data
7. **One concern per commit** — Keep commits focused on a single logical change

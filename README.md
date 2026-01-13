# AI Context Rules ✅

A concise, deterministic set of rules and templates for storing, synchronizing, and switching "active" and "project" context for AI agents working inside a repository. The goal is to make it trivial for any agent (or human reviewer) to resume or bootstrap work reliably across chat sessions.

---

## 🚀 Quick summary

- **Purpose:** Define a simple, actionable workflow for saving and updating task state (the _active context_) and project onboarding info (the _project context_). 
- **Primary files:** `ai_memory/active_context.md` (startup state), `ai_memory/project_context.md` (project onboarding), and doc modules in `docs/context_rules/`.

---

## 🔧 Features

- Canonical structure and mandatory template for `active_context` so resuming work is deterministic and fast.
- Procedures for context synchronization, switching, archiving and staleness handling.
- Templates and helper docs: `active_context_template.md`, `project_context_template.md`, and policy docs (`sync.md`, `switching.md`, `multi_task.md`, etc.).
- Guidance for what to record (meta, plan, progress, breadcrumbs, guardrails, quick-resume block) and when to update it.

---

## 📁 Repository structure (important files)

- `ai_instructions.md` — high-level startup instruction: always load `ai_memory/active_context.md`.
- `context_rules_concept.md` — conceptual overview and definitions.
- `docs/context_rules/` — detailed rules and templates (sync, switching, multi-task, staleness, hygiene/security).
- `ai_memory/` — runtime artifacts (active/project contexts, archived contexts, plans).
- `LICENSE` — repository license.

---

## 🧭 Quick start (for agents and contributors)

1. On every new chat start, **always** load and follow `ai_memory/active_context.md`.
2. Optionally load `ai_memory/project_context.md` to refresh repo-level onboarding info.
3. After a meaningful change (plan change, repo edit, blocker discovered, decision made) **synchronize** `ai_memory/active_context.md` immediately.
4. If the active context is stale or irrelevant to new intent, follow the switching protocol (`docs/context_rules/switching.md`) to archive and bootstrap a new context.
5. Keep the **Quick Resume** block at the end of `active_context` up-to-date: it should let someone jump in within 10 seconds.

---

## 📝 Contributing

- Please open issues or PRs for improvements, clarifications, or new templates.
- Follow the repository's conventions when editing context templates and rules: focus on necessary sufficiency, avoid duplication, and keep the `active_context` actionable.
- For large changes that affect workflows, update docs under `docs/context_rules/` and provide an example or migration guide.

---

## ✅ Recommended practices

- Prefer recording state over history; move logs and long traces to session history artifacts.
- Keep `active_context` focused: one primary `Current Task`, at most a few `Secondary Tasks` (use archival when needed).
- Use stable `task_id` values and clear guardrails to make automation reliable.

---

## License

This project is licensed under the terms in `LICENSE`.


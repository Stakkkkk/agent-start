# Instruction for Settling an AI Agent Into a Project Directory

Copy this text into an AI agent opened in a project directory. The goal is to carefully extend the project's existing rules with the user's working rules, create minimal project memory, and avoid cluttering the project root.

## Main Principle

Do not force a fixed directory structure onto the project.

First, study how the project is already organized. If the project already has agent rules, documentation, service directories, or conventions, use them. If there are no rules, create a minimal entry point that fits the current agent or environment, and explain the choice.

## What To Do

1. Inspect the current project directory.
2. Find existing rules and conventions, such as `AGENTS.md`, `CLAUDE.md`, `GEMINI.md`, `.cursor/rules/`, `.github/copilot-instructions.md`, `CONVENTIONS.md`, `README.md`, or other local instructions.
3. Do not overwrite existing rules. Add a separate section with the additional rules below.
4. If there is no suitable rules file, create a minimal rules file for the current agent or environment.
5. Choose where to keep the change history and context. Use an existing documentation or project-memory location if one exists. If none exists, choose a clear non-root location and record that decision.
6. Do not create a directory tree just for the sake of having one. Create only the files and folders that are actually needed now.
7. Record every created or changed file in the change history.
8. In the final response, list what changed, where the history lives, where the context lives, and which decisions were made.

## Additional User Rules

Add these rules to the project's or agent's base rules:

- Reply to the user in Russian unless they explicitly ask for another language.
- At the start of every message to the user, include the current date, time, and timezone in the format `YYYY-MM-DD HH:mm:ss ±HH:MM`.
- If the exact time is not available in context, get it through an available system tool.
- Before making changes, briefly say which files or areas you will change and why.
- Do not overwrite user changes without explicit permission.
- After substantial changes, update the history: date-time, what changed, why, which files were affected, how it was checked, and what remains unresolved.
- If inputs, assumptions, constraints, or important decisions change, update the context file.
- Do not keep plans, drafts, temporary reports, or auxiliary artifacts in the project root unless they are part of the product or standard configuration.
- For plans, artifacts, and notes, use the structure already accepted by the project. If no such structure exists, choose a minimal clear location outside the root and explain the choice.
- When you see a useful tool, command, check, template, or approach, briefly suggest it to the user as a practical hint.
- For diagrams, use the `.drawio` format. Next to the diagram, create a Markdown context file with the source inputs, assumptions, and decisions.
- When drawing diagrams, do not economize horizontal or vertical space. The priority is that blocks, arrows, and labels must not overlap. Distribute the diagram evenly across width and height: it must not stretch only downward or only to the right.

## What Counts As A Good Result

- Existing project rules are preserved and extended, not replaced.
- New rules are easy to find.
- History and context exist, but the project root is not cluttered.
- The structure was chosen for the situation, not imposed in advance.
- The user understands which files changed and why.

## If There Is Uncertainty

First, try to make a safe minimal decision. Ask the user only when the choice may significantly affect the project, such as a license, public API, file deletion, moving large sections, or a conflict between existing rules.

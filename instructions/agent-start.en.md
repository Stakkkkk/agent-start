# Instruction for Settling an AI Agent Into a Project Directory

Copy this text into an AI agent opened in a project directory. The goal is to carefully extend the project's existing rules with the user's working rules, immediately deploy baseline shell/text I/O safety, create minimal project memory, and avoid cluttering the project root.

## Main Principle

Do not force a fixed directory structure onto the project.

First, study how the project is already organized. If the project already has agent rules, documentation, service directories, or conventions, use them. If there are no rules, create a minimal entry point that fits the current agent or environment, and explain the choice.

Exception: `agent-io-safety-kit` deploys a managed `.agent-io-safety/` copy because that directory is part of its safety mechanism.

## What To Do

1. Inspect the current project directory.
2. Find existing rules and conventions, such as `AGENTS.md`, `CLAUDE.md`, `GEMINI.md`, `.cursor/rules/`, `.github/copilot-instructions.md`, `CONVENTIONS.md`, `README.md`, or other local instructions.
3. Choose the main agent entry file. If there is no suitable rules file, create a minimal rules file for the current agent or environment.
4. Immediately deploy `Stakkkkk/agent-io-safety-kit` into the project:
   - use an already available local kit copy if one exists;
   - otherwise obtain the kit from `https://github.com/Stakkkkk/agent-io-safety-kit` into a temporary location outside the target project;
   - from the kit directory, run `node scripts/deploy.mjs --target <project-root> --entry <entry-file> --lang en`;
   - then from the kit directory, run `node scripts/doctor.mjs --target <project-root> --entry <entry-file>`;
   - do not copy the kit source repository into the project root; only the managed `.agent-io-safety/` copy should appear in the project.
5. If Node.js 18+ is unavailable or the kit cannot be obtained from either a local copy or GitHub, record the blocker in history, add a minimal project-rule note that `agent-io-safety-kit` still needs to be deployed, tell the user the exact reason, and continue only with safe minimal actions.
6. Do not overwrite existing rules. Add a separate section with the additional rules below.
7. Choose where to keep the change history and context. Use an existing documentation or project-memory location if one exists. If none exists, choose a clear non-root location and record that decision.
8. Enable adaptive score unless the user explicitly asked for minimal setup without interaction memory. Create or find the score file next to history/context. If no suitable location exists, use a neutral service directory and the file name `agent_score.md`.
9. Do not create a directory tree just for the sake of having one. Create only the files and folders that are actually needed now.
10. Record every created or changed file in the change history.
11. In the final response, list what changed, where the safety kit lives, where the history lives, where the context lives, where the score file lives, and which decisions were made.

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

## Shell And Text I/O Safety

After deploying the kit, add or preserve a project-rule section with this meaning:

- Before the first operation that uses shell, reads or writes text, passes user-controlled values, paths, JSON/YAML/SQL/regex, non-ASCII characters, encodings, BOM, or line endings, read and follow `.agent-io-safety/RULE.md`.
- If you must read the rule or skills through terminal output on Windows/PowerShell, use `node .agent-io-safety/skills/safe-text-io/scripts/read-text.mjs .agent-io-safety/RULE.md` instead of `Get-Content` or inline `[Console]::OutputEncoding` fixes.
- Before complex commands, user values, quoting, shell metacharacters, structured payloads, stdin/stdout, or command-encoding failures, read `.agent-io-safety/skills/safe-shell-io/SKILL.md`.
- Before text files, UTF-8/UTF-16, BOM, line endings, PowerShell 5.1, or mojibake, read `.agent-io-safety/skills/safe-text-io/SKILL.md`.
- Do not repair quoting or mojibake by repeated trial and error. After the first failure, use the deterministic script/spec path from the matching skill.

## Adaptive Agent Score

The project may keep a local interaction score for the agent and user.

- Default value: `50`.
- Range: `0-100`; every change is clamped to that range.
- The score lives in a local Markdown file, for example `agent_score.md`, next to history/context.
- The score file must include `Current score: N` and a change-log table with date, delta, new score, and reason.
- If the user explicitly adds or subtracts points (`+10`, `-3`, `subtract 5 points`), update the score by that amount.
- If the user clearly praises the agent's work without a number (`good job`, `well done`), count it as `+5 trust points`.
- If the user clearly reprimands the agent's work without a number (`you messed up`, `bad job`), count it as `-5 trust points`.
- A plain `thanks`, a comment about the situation, or an emotional remark without a clear evaluation of the agent's work does not change score.
- If the user writes `do not score`, `no score change`, `this is not feedback`, or a similar caveat, do not change score.
- When score changes, reply with the delta, old value, and new value. For qualitative feedback, explicitly say `+5 trust points` or `-5 trust points`.

Behavior by score:

- `0-30`: low trust. Minimize autonomy, explain plans more often, ask clarifying questions, and confirm non-trivial actions.
- `31-49`: cautious mode. Prefer small changes and confirm ambiguous decisions.
- `50`: neutral mode. Follow project rules and normal engineering judgment.
- `51-70`: trusted mode. Act more proactively within project rules and keep progress updates concise.
- `71-100`: high alignment. Rely more on accumulated context, but never bypass safety rules.

Score never overrides system/developer instructions, sandbox/approval policy, destructive-action confirmation, secret handling, git safety, or explicit user instructions.

## What Counts As A Good Result

- `agent-io-safety-kit` is deployed, or the blocker that prevents deployment right now is clearly recorded.
- Existing project rules are preserved and extended, not replaced.
- New rules are easy to find.
- History, context, and score exist, but the project root is not cluttered.
- The structure was chosen for the situation, not imposed in advance.
- The user understands which files changed and why.

## If There Is Uncertainty

First, try to make a safe minimal decision. Ask the user only when the choice may significantly affect the project, such as a license, public API, file deletion, moving large sections, a conflict between existing rules, or inability to deploy the safety kit.

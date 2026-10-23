# AGENTS.md

Instructions for working with this repository.

## 1. Task Workflow and Decomposition

- Create a plan for every user request that requires project changes. The plan must be tracked as a GitHub Issue.
- Present the proposed plan to the user and obtain approval before creating the Issue.
- Implement the approved plan in a separate Git branch and submit a Pull Request (PR) that fulfills the Issue.
- A plan is considered successfully completed only when the user explicitly confirms it or merges the corresponding PR.
- If a task is too large or can be divided into independent phases, split it into multiple Issues linked to the main Issue.
- Propose the sequence of phases to the user and obtain approval before creating the Issues.
- Execute each approved phase separately. Do not proceed to the next phase until the user confirms the completion of the current phase.
- If blocked for an extended period, stop and ask the user for guidance rather than continuing without a clear path forward.
- If a requirement is ambiguous and different interpretations could lead to substantially different implementations, do not guess silently. Identify the ambiguity and ask for clarification.
- For minor ambiguities, prefer the smallest change consistent with the existing project.

## 2. Project Documentation

- `PROJECT.md` contains the high-level project description, architecture, and purpose.
- Update `PROJECT.md` whenever user-facing functionality is added or its behavior changes.
- `CHANGELOG.md` must briefly document all changes, bug fixes, new features, and other relevant updates, with links to the corresponding Issues and Pull Requests.
- `README.md` is intended for human readers, not agents. Modify it only with the user's explicit permission and instructions.

## 3. Code Style and Rules

- Keep the code modular, testable, and consistent with the conventions of the chosen programming language.
- Use simple functions for stateless functionality.
- Use classes or structs with attributes and methods when state is required.
- Test the exported public contract of each module rather than its internal implementation details, which may change frequently.
- Use Dependency Injection to decouple modules and support reuse and independent testing.
- Maintain a single application entry point that initializes, starts, and coordinates modules in a clear sequence.
- Use current documentation and the latest stable, compatible versions of dependencies and libraries.
- After each task, run the relevant tests and build the project to verify that nothing is broken.
- Run available linters and formatters as well.
- Define all project management commands as `Makefile` targets, including test, build, lint, format, run, and stop. Use these targets instead of ad-hoc commands.

## 4. Safety and Git Rules

- Never store secrets, credentials, passwords, or `.env` files containing secrets in the codebase.
- Do not delete files or branches unless required by the task and explicitly confirmed by the user.
- Never push directly to `master` or `main` unless explicitly requested by the user.
- Never delete or rewrite Git history.

## 5. Project specific rules

None.





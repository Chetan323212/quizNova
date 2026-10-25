# Contributing Guidelines

Thank you for your interest in contributing to the Live Quiz Platform!

This project is developed collaboratively by the maintainer and student contributors. Our goal is to build a reliable application while learning professional software development practices.

Every contribution should improve the project, follow its conventions, and be easy for another developer to understand and maintain.

## Table of Contents

- [Getting Started](#getting-started)
- [Finding a Task](#finding-a-task)
- [Forking the Repository](#forking-the-repository)
- [Branching Strategy](#branching-strategy)
- [Commit Convention](#commit-convention)
- [Development Guidelines](#development-guidelines)
- [Testing Requirements](#testing-requirements)
- [Pull Request Process](#pull-request-process)
- [Code Review](#code-review)
- [AI-Assisted Development](#ai-assisted-development)
- [Contributor Expectations](#contributor-expectations)

## Getting Started

Before contributing:

1. Read the root `README.md`.
2. Review `ARCHITECTURE.md` to understand the application.
3. Set up the project locally by following the setup instructions.
4. Check the existing GitHub Issues and project board.
5. Read the requirements and acceptance criteria of your assigned issue.

If something is unclear, ask questions in the relevant issue before making assumptions.

## Finding a Task

All planned features, bug fixes, improvements, and technical tasks should be tracked through GitHub Issues.

Each issue should describe:

- The problem or requirement
- The expected behavior
- Acceptance criteria
- Relevant technical context
- Testing expectations, where applicable

Do not start a substantial feature without confirming that the task is available to you.

If multiple contributors are assigned the same feature, each contributor should implement an independent solution and submit a separate pull request.

Do not copy another contributor's implementation or use another person's unpublished solution as the basis for your own submission.

## Forking the Repository

We use the fork-based contribution workflow.

### 1. Fork the repository

Create your own fork of the original repository through GitHub.

### 2. Clone your fork

    git clone <your-fork-url>
    cd <repository-directory>

### 3. Add the original repository as upstream

    git remote add upstream <original-repository-url>

Verify the remotes:

    git remote -v

Your `origin` should point to your fork, while `upstream` should point to the original project.

### 4. Synchronize with the latest main branch

Before beginning a new task:

    git switch main
    git fetch upstream
    git merge upstream/main
    git push origin main

This updates your local `main` and your fork with the latest upstream changes.

If your local `main` has no unique commits, you may instead reset it to `upstream/main`. Do not do this if you have commits you need to preserve.

## Branching Strategy

The project follows a simplified GitHub Flow.

The `main` branch is the stable branch. Contributors must not push directly to the original repository's `main` branch.

Create a separate branch for each issue or task.

### Branch naming format

    <type>/<issue-number>-<short-description>

Examples:

    feature/123-live-leaderboard
    fix/145-duplicate-submission
    refactor/152-quiz-service
    test/160-quiz-api
    docs/170-contributor-guide
    chore/180-update-dependencies

Use lowercase names and hyphens between words.

### Create your branch

Start from the latest `main` branch:

    git switch main
    git pull upstream main
    git switch -c feature/123-live-leaderboard

Make sure your fork is up to date before starting work.

### Push your branch

    git push -u origin feature/123-live-leaderboard

Push subsequent changes to the same branch as needed.

## Commit Convention

We follow Conventional Commits.

### Format

    <type>(<scope>): <description>

Examples:

    feat(quiz): add question timer
    fix(quiz): prevent duplicate submissions
    refactor(api): extract quiz service
    test(quiz): cover score calculation
    docs(setup): explain local installation
    perf(leaderboard): optimize score updates
    ci(github): add pull request checks
    chore(repo): update editor configuration

### Commit types

| Type | Purpose |
|---|---|
| `feat` | Introduce a feature |
| `fix` | Correct a bug |
| `refactor` | Improve internal code without intentionally changing behavior |
| `test` | Add or modify tests |
| `docs` | Update documentation |
| `style` | Formatting-only changes |
| `perf` | Improve performance |
| `build` | Change build tooling or dependencies |
| `ci` | Change CI/CD configuration |
| `chore` | General maintenance |

### Commit message rules

- Use lowercase types and scopes.
- Write concise, meaningful descriptions.
- Use the imperative form, such as `add`, `fix`, or `update`.
- Do not end the subject with a period.
- Keep each commit focused on one logical change.
- Avoid vague messages such as `update code`, `final changes`, or `fixed everything`.

Good example:

    feat(quiz): add answer submission endpoint
    test(quiz): cover invalid submissions
    fix(quiz): reject submissions after timeout

A commit should represent one logical change, not necessarily one file.

## Development Guidelines

All contributions must follow the existing project structure and conventions.

### General rules

- Read the existing implementation before changing it.
- Avoid unrelated changes in the same pull request.
- Use descriptive variable and function names.
- Keep functions and components focused on a clear responsibility.
- Handle relevant error cases.
- Validate and sanitize untrusted input where appropriate.
- Avoid duplicating existing functionality.
- Do not commit generated files, dependencies, secrets, or local configuration unless explicitly required.
- Update documentation when behavior, setup, or APIs change.

### Frontend guidelines

- Keep UI components understandable and focused.
- Handle loading, success, empty, and error states where appropriate.
- Avoid unnecessary duplicate state.
- Make sure the UI responds correctly to API and real-time updates.
- Follow existing accessibility and styling conventions.

### Backend guidelines

- Validate request data before processing it.
- Keep business logic separate from HTTP handlers where the existing architecture supports it.
- Return consistent responses and appropriate HTTP status codes.
- Handle database and external-service failures.
- Enforce authorization on the server.
- Never trust client-provided scores, user roles, or other security-sensitive values.

### Real-time functionality

For Socket.IO or WebSocket features:

- Validate session membership and permissions.
- Handle disconnects and reconnections appropriately.
- Prevent duplicate or invalid submissions where required.
- Ensure clients cannot arbitrarily change authoritative quiz state or scores.
- Avoid broadcasting private information to unauthorized participants.

## Testing Requirements

Before submitting a pull request:

1. Run the relevant tests.
2. Run the configured linter, if available.
3. Run the build or type checks, if configured.
4. Test the affected user flow.
5. Add tests for new functionality and bug fixes where appropriate.

For a bug fix, include a test that demonstrates the corrected behavior whenever practical.

For real-time features, consider concurrent submissions, duplicate events, invalid session states, and disconnect scenarios.

Include the commands you ran and their results in your pull request. Never report tests as passing when they have not been executed.

## Pull Request Process

### 1. Open a pull request

Submit your PR against the original repository's `main` branch.

Use a descriptive title, following the commit convention where practical.

Example:

    feat(leaderboard): add real-time score updates

### 2. Link the issue

Reference the relevant GitHub Issue in the PR description.

For example:

    Closes #123

Only use an auto-closing keyword when the PR is intended to close that issue. If multiple contributors are competing to implement the same feature, do not close the shared issue until the maintainer decides the outcome.

### 3. Explain the change

Your PR should explain:

- What changed
- Why the change is needed
- How the implementation works
- How you tested it
- Any limitations or follow-up work
- Screenshots or recordings for UI changes, where relevant

### 4. Respond to feedback

The maintainer may approve the PR, request changes, or close it.

If changes are requested, make them on the same branch and push the updates. GitHub will update the existing PR automatically.

### 5. Merge policy

Only the maintainer or an explicitly authorized maintainer may merge contributions into `main`.

The project normally uses Squash and merge to maintain a readable history.

Not every submitted PR will be merged. Competing implementations may be evaluated against the same acceptance criteria, code quality, correctness, tests, security, and maintainability.

## Code Review

Code review is a learning opportunity.

Review feedback should be respectful, specific, and focused on the implementation rather than the individual.

Contributors should:

- Explain their design choices when asked.
- Understand the code they submit.
- Address review comments constructively.
- Ask for clarification when feedback is unclear.
- Avoid taking technical feedback personally.

The maintainer makes the final decision on whether a contribution is ready to merge.

## AI-Assisted Development

AI coding tools may be used as development aids, but contributors remain responsible for their submissions.

Contributors must:

- Understand the code they submit.
- Verify generated code rather than trusting it blindly.
- Test AI-generated implementations.
- Review security, correctness, and maintainability.
- Avoid submitting code they cannot explain.
- Never send private credentials, student information, or confidential project data to unauthorized AI tools.
- Disclose significant AI assistance when requested by the issue or maintainer.

AI-generated code is reviewed using the same quality standards as manually written code.

## Contributor Expectations

All contributors are expected to:

- Communicate respectfully.
- Follow the contribution process.
- Be honest about testing and implementation status.
- Respect other contributors' work.
- Follow the project's Code of Conduct.
- Keep pull requests focused and understandable.
- Accept that the maintainer makes final merge decisions.

Thank you for helping make the Live Quiz Platform better!
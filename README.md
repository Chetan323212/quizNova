# Live Quiz Platform

An open-source, real-time quiz platform built with the MERN stack, designed for interactive learning, live assessments, and AI-assisted evaluation.

This project is developed collaboratively by the instructor and student contributors. It is intended to be used in a real educational environment, tested with actual users, and improved through an open-source development workflow.

> **Project status:** Under active development. Features, APIs, and architecture may evolve as the project progresses.

## Table of Contents

- [About the Project](#about-the-project)
- [Goals](#goals)
- [Planned Features](#planned-features)
- [Technology Stack](#technology-stack)
- [Project Structure](#project-structure)
- [Getting Started](#getting-started)
- [Environment Variables](#environment-variables)
- [Contributing](#contributing)
- [Development Workflow](#development-workflow)
- [Testing](#testing)
- [Security](#security)
- [License](#license)

## About the Project

The Live Quiz Platform aims to make classroom assessments more interactive by allowing instructors to create and conduct quizzes while students participate in real time.

The project also explores AI-assisted assessment workflows, including question generation and subjective-answer evaluation.

This is a real development project, not just a demonstration application. Contributors work with an existing codebase, collaborate through Git and GitHub, submit pull requests, review code, write tests, and improve the application incrementally.

## Goals

- Build a reliable platform for live quizzes and classroom assessments.
- Support real-time interactions between instructors and students.
- Maintain readable, modular, and testable code.
- Introduce contributors to professional software development practices.
- Explore responsible applications of AI in education.
- Develop and test features in a real educational environment.

## Planned Features

The following features represent the project direction. Their implementation status should be tracked through GitHub Issues and the project board.

- [ ] Instructor quiz creation and management
- [ ] Student participation in quiz sessions
- [ ] Live question delivery and answer submission
- [ ] Timers and session-state management
- [ ] Real-time leaderboard and score updates
- [ ] Quiz results and performance summaries
- [ ] Authentication and role-based access
- [ ] AI-assisted question generation
- [ ] AI-assisted subjective-answer evaluation
- [ ] Automated tests and continuous integration

A feature should be considered complete only when its acceptance criteria are satisfied and the relevant changes have been reviewed and merged.

## Technology Stack

The intended technology stack includes:

- **MongoDB:** Persistent application data
- **Express.js:** Backend HTTP APIs
- **React:** User interface
- **Node.js:** Backend JavaScript runtime
- **Socket.IO or WebSockets:** Real-time communication, where required
- **AI provider integration:** AI-assisted functionality, introduced through a controlled backend interface

The exact libraries and versions used by the current implementation should be documented in the project's dependency files.

## Project Structure

The following is an example structure. Update it to reflect the actual repository.

    .
    ├── client/             # React frontend
    ├── server/             # Node.js and Express backend
    ├── docs/               # Additional project documentation
    ├── .github/            # GitHub templates and CI workflows
    ├── .env.example        # Safe environment-variable template
    ├── .gitignore
    ├── ARCHITECTURE.md
    ├── CONTRIBUTING.md
    ├── LICENSE
    └── README.md

## Getting Started

### Prerequisites

Install the following before setting up the project:

- Git
- Node.js (use the version specified by the project, if configured)
- npm
- MongoDB or access to an authorized development MongoDB instance

### 1. Fork and clone the repository

Fork the repository on GitHub, then clone your fork:

    git clone <your-fork-url>
    cd <repository-directory>

Add the original repository as the upstream remote:

    git remote add upstream <original-repository-url>

Verify your remotes:

    git remote -v

### 2. Install dependencies

Install the dependencies for each application directory that contains its own `package.json`.

For example, if both `client/` and `server/` have separate package files:

    cd client
    npm install

    cd ../server
    npm install

Use the package manager and lockfile established by the project. If the repository uses npm workspaces or a different layout, follow the actual project configuration instead.

### 3. Configure environment variables

Create local environment files based on `.env.example`.

Do not commit your local `.env` files or real credentials.

See [Environment Variables](#environment-variables) and the project setup documentation for required configuration.

### 4. Start the application

Run the frontend and backend using the scripts defined in their respective `package.json` files.

For example, if both applications provide a development script:

    cd server
    npm run dev

In a separate terminal:

    cd client
    npm run dev

The actual commands depend on the scripts configured in the repository.

## Environment Variables

Document every required environment variable in `.env.example`, including a short description where necessary.

Typical examples may include:

- `PORT` — Backend server port
- `MONGODB_URI` — Development database connection string
- `CLIENT_URL` — Allowed frontend origin
- `AI_API_KEY` — API key for the configured AI provider, if applicable

These names are illustrative. Use the actual variable names required by the implementation.

Never commit real secrets. AI provider credentials must remain on the backend and must not be exposed to the browser.

## Contributing

Contributions from students and the wider open-source community are welcome.

Before contributing:

1. Read [CONTRIBUTING.md](CONTRIBUTING.md).
2. Check existing issues before starting work.
3. Discuss substantial changes before implementing them.
4. Create a feature branch for your assigned issue.
5. Follow the commit message convention.
6. Submit a pull request with testing evidence.

All contributions are reviewed before they are merged into `main`. The maintainer makes the final merge decision based on requirements, correctness, readability, tests, security, and maintainability.

For educational tasks assigned to multiple students, each contributor should implement the task independently unless the issue specifies otherwise.

## Development Workflow

The project follows a simplified GitHub Flow:

- `main` contains the stable, reviewed codebase.
- Contributors create task-specific branches.
- Changes are submitted through pull requests.
- Automated checks must pass before merging.
- The maintainer reviews and merges approved changes.

See [CONTRIBUTING.md](CONTRIBUTING.md) for the complete workflow.

## Testing

Contributors are expected to run the relevant tests before submitting a pull request.

Depending on the affected code, this may include:

- Unit tests
- API or integration tests
- Frontend tests
- Real-time interaction tests
- Linting and build checks
- Manual verification of relevant user flows

Do not claim that a test has passed unless it has actually been executed.

## Security

Do not commit passwords, API keys, access tokens, private student information, or production database credentials.

Report security vulnerabilities privately using the process described in [SECURITY.md](SECURITY.md), if configured.

All contributions must follow the project's security and privacy requirements.

## License

See the [LICENSE](LICENSE) file for the terms under which this project may be used, modified, and distributed.
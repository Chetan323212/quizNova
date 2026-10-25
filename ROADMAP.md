# Roadmap

This roadmap outlines the planned development of the project, from building the user interface to implementing backend functionality, migrating to TypeScript, and integrating AI capabilities.

The project is developed incrementally. Each phase builds on the previous one, giving contributors opportunities to learn and practice real-world software development workflows.

**Note:** This roadmap represents the current direction of the project. Features and priorities may change as development progresses.

## Phase 1: User Interface (UI)

**Goal:** Build the user-facing interface and establish the visual structure of the application.

### Planned work

- Set up the frontend project structure.
- Create a consistent layout and reusable UI components.
- Build the main pages and navigation.
- Develop quiz creation and quiz participation interfaces.
- Build the live quiz interface, including question display, answer selection, timers, and leaderboard layouts.
- Add loading, empty, success, and error states where appropriate.
- Make the interface responsive across common screen sizes.
- Use mock data where backend functionality is not yet available.

### Expected outcome

A functional frontend prototype that allows users to navigate the application and experience the planned quiz workflows using mock data.

## Phase 2: Node.js Backend

**Goal:** Implement server-side functionality and connect the frontend to a persistent backend.

### Planned work

- Set up the Node.js and Express backend.
- Establish the MongoDB database connection.
- Define the initial data models and relationships.
- Implement user authentication and authorization.
- Create APIs for quiz creation, retrieval, editing, and participation.
- Store quiz questions, answers, submissions, and session information.
- Implement quiz scoring and leaderboard calculations.
- Integrate real-time communication for live quiz sessions and leaderboard updates.
- Add request validation and consistent error handling.
- Connect the frontend to the backend APIs.

### Expected outcome

A working full-stack application where quiz data is stored persistently, users can participate in quizzes, and live sessions support real-time updates.

## Phase 3: Migration to TypeScript

**Goal:** Improve type safety, maintainability, and developer experience by migrating the JavaScript codebase to TypeScript.

### Planned work

- Configure TypeScript for the frontend and backend.
- Establish shared coding and type-definition conventions.
- Migrate existing JavaScript files incrementally.
- Define types and interfaces for users, quizzes, questions, submissions, and quiz sessions.
- Add types for API requests, responses, and error structures.
- Type real-time events and their payloads.
- Introduce appropriate types for database models and service functions.
- Enable stricter compiler settings progressively.
- Remove unnecessary `any` usage and resolve type errors.

### Expected outcome

A TypeScript-based application with clearer contracts between modules, improved editor support, and fewer errors caused by incompatible data structures.

**Migration approach:** Migrate incrementally rather than rewriting the entire application at once. Keep the application usable as each part is converted.

## Phase 4: AI Features

**Goal:** Integrate AI capabilities that help educators create learning material and evaluate student responses.

### Planned work

- Design an AI integration layer that can communicate with an AI provider.
- Generate quiz questions from educator-provided content.
- Support AI-assisted generation of multiple-choice and other question types.
- Allow educators to review and edit generated questions before publishing them.
- Explore AI-based evaluation of subjective answers using defined evaluation criteria.
- Provide feedback and explanations to help learners understand their mistakes.
- Handle AI provider errors, timeouts, and usage limits.
- Protect API keys and validate inputs and outputs.
- Evaluate the quality of generated questions and AI-assisted assessments through manual review.

### Expected outcome

An application that helps educators create assessments more efficiently and explore AI-assisted evaluation while keeping educators in control of the learning experience.

## Development Principles

The project will follow these principles throughout development:

- **Incremental development:** Build and improve the application in manageable steps.
- **Code review:** All contributions must be submitted through pull requests and reviewed before merging.
- **Consistent conventions:** Follow the project's agreed branching, commit, and coding conventions.
- **Manual verification:** Contributors must run the application and verify relevant functionality before submitting changes.
- **Maintainability:** Prefer understandable, reusable code over unnecessary complexity.
- **Learning through contribution:** Tasks should help contributors understand both the implementation and the development workflow.
- **Documentation:** Update relevant documentation when a change affects setup, usage, architecture, or project conventions.

Automated testing and continuous integration may be introduced as the project matures.

## How Work Will Be Organized

Work will be divided into small, clearly defined issues. Each issue should describe the problem, expected behavior, and acceptance criteria.

When multiple contributors work on the same feature:

1. Each contributor implements the feature on a separate branch or fork.
2. Each contributor opens an independent pull request.
3. The maintainer reviews the implementations against the same acceptance criteria.
4. The selected implementation is merged into the main branch.
5. Useful ideas from other implementations may be incorporated through follow-up issues or pull requests.

The `main` branch should remain the stable, reviewed version of the project.

## Current Focus

Development will begin with **Phase 1: User Interface**. Later phases will be taken up as the project evolves and the current phase provides a suitable foundation.

The roadmap is intentionally flexible. Individual issues and pull requests—not the roadmap alone—will define the precise scope of each contribution.

# agentic-skills-for-quarkus

GitHub Copilot and Claude Code skills for building Quarkus applications.

This repository provides a small set of focused skills that help an AI assistant guide you through two common kinds of work:

- **Bootstrapping Quarkus applications** with the right platform, extensions, and runtime choices.
- **Scaffolding DDD and Hexagonal Architecture components** inside Quarkus projects.

Each skill is designed to work as an agent instruction set. You ask for a task in natural language, the assistant loads the relevant skill, gathers the required details, and then generates the appropriate project structure, code, or configuration.

## Available skills

### `quarkus-app`
Use this skill when you want to create or maintain a Quarkus application.

It helps with:
- Creating a new Quarkus project
- Choosing the build tool and Java version
- Adding or updating extensions
- Keeping versions aligned with the latest Quarkus platform
- Supporting Red Hat Build of Quarkus when needed

### `quarkus-ddd`
Use this skill when you want to model a new bounded context or add DDD tactical patterns to a Quarkus application.

It helps with:
- Bounded contexts and subdomains
- Aggregates and value objects
- Commands, domain events, and result records
- Application services
- REST endpoints and DTOs
- Persistence entities and repositories
- Hexagonal Architecture / Ports and Adapters structure

## Repository structure

- `skills/quarkus-app/` — Quarkus application scaffolding and maintenance guidance
- `skills/quarkus-ddd/` — DDD and Hexagonal Architecture scaffolding guidance

## How to use these skills with Claude

This repository is primarily intended for **Claude Code** skill installation.

### Install from GitHub

```bash
claude mcp add-skill https://github.com/jeremyrdavis/agentic-skills-for-quarkus/tree/main/skills/quarkus-app
claude mcp add-skill https://github.com/jeremyrdavis/agentic-skills-for-quarkus/tree/main/skills/quarkus-ddd
```

### Install from a local clone

```bash
git clone https://github.com/jeremyrdavis/agentic-skills-for-quarkus.git
claude mcp add-skill ./agentic-skills-for-quarkus/skills/quarkus-app
claude mcp add-skill ./agentic-skills-for-quarkus/skills/quarkus-ddd
```

### Example prompts

- “Create a new Quarkus REST API with PostgreSQL persistence.”
- “Add Kafka messaging and health checks to my Quarkus app.”
- “Create an orders bounded context with an Order aggregate and value objects for line items.”
- “Add a new aggregate to the catalog subdomain.”

Claude will load the matching skill and use its instructions to gather the right inputs before generating code.

## How to use these skills with Codex

Codex can use the same skill content as guidance for generating or modifying code in this repository or in your Quarkus projects.

### Typical workflow

1. Point Codex at the repository or copy the relevant skill into your working context.
2. Ask for the task you want done in natural language.
3. Let Codex follow the skill instructions to gather missing details, decide on structure, and produce the output.

### Example prompts

- “Use the Quarkus app skill to scaffold a new service with REST and PostgreSQL.”
- “Use the DDD skill to add a new payments bounded context.”
- “Follow the repo’s Quarkus DDD conventions and generate the aggregate, command, event, service, and endpoint.”

### Notes for Codex users

- The skills are written as reusable instructions, so Codex can treat them as a playbook for Quarkus work.
- If you are editing this repository, keep new skills aligned with the existing folder layout under `skills/`.
- When a task involves both application bootstrap and DDD modeling, use `quarkus-app` first, then `quarkus-ddd`.

## Prerequisites

- Java 25 or your preferred version
- Maven or Gradle
- Quarkus CLI recommended for app scaffolding
- Claude Code or Codex, depending on your workflow

## Contributing

If you add new skills, keep them focused, well-documented, and consistent with the existing naming and directory conventions.

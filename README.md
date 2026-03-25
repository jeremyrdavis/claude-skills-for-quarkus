# claude-skills-for-quarkus

Claude Code skills for building Quarkus applications. Includes skills for project scaffolding and Domain-Driven Design with Hexagonal Architecture.

## Skills

### quarkus-app

Scaffolds and maintains Quarkus applications. Handles project generation (CLI or Maven plugin), extension management, version upgrades, and Red Hat Build of Quarkus (RHBQ) support.

### quarkus-ddd (ddd-quarkus)

Scaffolds DDD tactical patterns — aggregates, value objects, commands, domain events, repositories, services, and endpoints — using Hexagonal Architecture (Ports and Adapters) in Quarkus projects.

## Prerequisites

- [Claude Code](https://docs.anthropic.com/en/docs/claude-code) installed and authenticated
- Java 25 (or your preferred version — skills will ask)
- [Quarkus CLI](https://quarkus.io/guides/cli-tooling) recommended (Maven plugin works as a fallback)
- Maven or Gradle

## Installation

Install skills directly from GitHub using the Claude Code CLI:

```bash
# Install both skills
claude mcp add-skill https://github.com/jeremyrdavis/claude-skills-for-quarkus/tree/main/quarkus-app
claude mcp add-skill https://github.com/jeremyrdavis/claude-skills-for-quarkus/tree/main/quarkus-ddd
```

Or clone the repository and install locally:

```bash
git clone https://github.com/jeremyrdavis/claude-skills-for-quarkus.git
claude mcp add-skill ./claude-skills-for-quarkus/quarkus-app
claude mcp add-skill ./claude-skills-for-quarkus/quarkus-ddd
```

## Usage Examples

### Create a new Quarkus application

```
> Create a Quarkus REST API with PostgreSQL persistence
```

Claude will use the **quarkus-app** skill to ask for your project parameters (groupId, artifactId, Java version, extensions) and generate the project using the Quarkus CLI.

### Add extensions to an existing project

```
> Add Kafka messaging and health checks to my Quarkus app
```

### Scaffold a DDD bounded context

```
> Create a new "orders" bounded context with an Order aggregate that has orderId, customer name, and a list of line items
```

Claude will use the **ddd-quarkus** skill to gather your domain details and scaffold the full Hexagonal Architecture — domain layer (aggregate, value objects, commands, events), infrastructure layer (REST endpoint, DTOs, event publisher), and persistence layer (JPA entities, Panache repository).

### Add a new aggregate to an existing context

```
> Add a Product aggregate to the catalog subdomain with name, description, and price
```

### Use both skills together

```
> Create a new Quarkus microservice for conference management with a Sessions bounded context
```

Claude will first scaffold the Quarkus project with the right extensions, then generate the DDD structure for the Sessions domain.

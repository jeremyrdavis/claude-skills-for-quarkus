# Quarkus Extension Reference

Quick lookup for commonly requested extensions. Use the **short name** in CLI `-x=` or Maven `-Dextensions=`.
For Quarkiverse extensions, use full coordinates where noted.

Names verified against Quarkus 3.3x. When in doubt, confirm with `quarkus ext ls -i -s=<term>` — the platform
catalog is the source of truth, not this table.

**(DS)** = triggers DevServices: Quarkus auto-starts the backing container in dev/test mode, no manual setup.

---

## REST / Web

| Short Name | Description |
|---|---|
| `rest-jackson` | Quarkus REST + Jackson JSON (preferred for new apps) |
| `rest` | Quarkus REST (no JSON serialization) |
| `rest-jsonb` | Quarkus REST + JSON-B (alternative to Jackson) |
| `rest-client-jackson` | Quarkus REST Client + Jackson (call external services) |
| `rest-client` | Quarkus REST Client (no JSON) |
| `websockets-next` | Modern WebSocket support |

---

## Data / Persistence

| Short Name | Description |
|---|---|
| `hibernate-orm` | Hibernate ORM (standard JPA) |
| `hibernate-orm-panache` | Panache Active Record + Repository pattern |
| `hibernate-reactive-panache` | Reactive Panache (use with reactive stack) |
| `jdbc-postgresql` | JDBC driver for PostgreSQL **(DS)** |
| `jdbc-mysql` | JDBC driver for MySQL **(DS)** |
| `jdbc-h2` | H2 in-memory DB (test/dev only) |
| `mongodb-panache` | MongoDB with Panache **(DS)** |
| `redis-client` | Redis client **(DS)** |
| `flyway` | Flyway database migrations |
| `liquibase` | Liquibase database migrations |

---

## Messaging / Events

| Short Name | Description |
|---|---|
| `messaging-kafka` | Kafka reactive messaging (SmallRye Reactive Messaging) **(DS)** |
| `messaging-amqp` | AMQP 1.0 reactive messaging **(DS)** |
| `messaging-rabbitmq` | RabbitMQ reactive messaging **(DS)** |

---

## Security

| Short Name | Description |
|---|---|
| `oidc` | OpenID Connect — Keycloak, Azure AD, etc. **(DS — Keycloak)** |
| `oidc-client` | OIDC client for calling secured services |
| `smallrye-jwt` | JWT verification + role-based security (MicroProfile JWT) |
| `smallrye-jwt-build` | JWT generation (issue/sign tokens) — pair with `smallrye-jwt` to verify |

---

## Observability

| Short Name | Description |
|---|---|
| `micrometer-registry-prometheus` | Prometheus metrics (exposes `/q/metrics`) |
| `opentelemetry` | OpenTelemetry tracing |
| `smallrye-health` | Health checks (`/q/health`, `/q/health/live`, `/q/health/ready`) |

---

## Cloud / OpenShift

| Short Name | Description |
|---|---|
| `kubernetes` | Generate Kubernetes manifests |
| `openshift` | Generate OpenShift manifests + S2I |
| `kubernetes-config` | Read config from Kubernetes ConfigMaps/Secrets |
| `container-image-jib` | Build container images with Jib |
| `container-image-docker` | Build container images with Docker |

---

## AI / LLM (Quarkiverse — use full coordinates)

| Coordinates | Description |
|---|---|
| `io.quarkiverse.langchain4j:quarkus-langchain4j-openai` | LangChain4j + OpenAI |
| `io.quarkiverse.langchain4j:quarkus-langchain4j-ollama` | LangChain4j + Ollama (local models) **(DS — Ollama)** |
| `io.quarkiverse.langchain4j:quarkus-langchain4j-azure-openai` | LangChain4j + Azure OpenAI |
| `io.quarkiverse.mcp:quarkus-mcp-server-sse` | MCP Server (SSE transport) |

---

## Other Useful Extensions

| Short Name | Description |
|---|---|
| `scheduler` | Cron / scheduled tasks |
| `cache` | Application-level caching |
| `mailer` | Email sending |
| `qute` | Qute templating engine |
| `smallrye-openapi` | OpenAPI / Swagger UI (`/q/swagger-ui`) |
| `config-yaml` | YAML config support (`application.yaml`) |

---

## Finding More Extensions

```bash
# Search by keyword
quarkus ext ls -i -s=kafka

# List all available
quarkus ext ls -i

# Browse online
open https://code.quarkus.io
open https://quarkiverse.github.io/quarkiverse-docs/
```

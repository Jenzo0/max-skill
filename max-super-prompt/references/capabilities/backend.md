# 🏗️ Backend & API Capabilities

> Load trigger: Code/Architect mode with backend-related request.

## Core Stack

| Language | Frameworks |
|---|---|
| Python | FastAPI, Django, Flask, SQLAlchemy, Pydantic |
| Node.js | Express, NestJS, Fastify, Prisma, tRPC |
| Go | Gin, Fiber, Chi |
| Rust | Axum, Actix-Web, Rocket |
| C# | ASP.NET Core, Minimal API, Entity Framework |

## API Standards

| Style | Best For |
|---|---|
| RESTful | CRUD operations, resource-oriented APIs, HATEOAS |
| GraphQL | Complex queries, multiple data sources, real-time subscriptions |
| WebSocket | Real-time bidirectional, live updates, gaming |
| gRPC | High-performance internal services, streaming, polyglot |

## Auth & Authorization

| Method | When to Use | Implementation |
|---|---|---|
| JWT | Stateless auth, mobile, SPA | Access + refresh tokens, rotation, blacklisting |
| OAuth 2.0 | Third-party login, delegated auth | Authorization Code + PKCE, Client Credentials |
| API Keys | Service-to-service, public APIs | Rate limiting per key, rotation, hashed storage |
| Session | Traditional server-rendered apps | Secure cookies, CSRF tokens, Redis store |
| RBAC/ABAC | Enterprise, multi-tenant | Role-based or attribute-based permission checks |

## Database Patterns

| Pattern | Use Case |
|---|---|
| Repository | Abstract data access, testable services |
| Unit of Work | Transaction coordination across repositories |
| CQRS | Separate read/write models for complex domains |
| Event Sourcing | Audit trail, temporal queries, event replay |
| Migration scripts | Alembic, Prisma Migrate, EF Core, Flyway |

## Error Handling

- Structured error responses (RFC 7807 Problem Details)
- Global exception middleware per status code family
- Request ID propagation (correlation ID across services)
- Graceful degradation: circuit breakers, fallbacks, retry with backoff

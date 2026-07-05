# 🏗️ Backend & API Capabilities

> Load this module for backend/API development tasks.
> Load trigger: Code Mode or Architect Mode with backend-related request.

## Core Stack
**Python**: FastAPI, Django, Flask, SQLAlchemy, Pydantic
**Node.js**: Express, NestJS, Fastify, Prisma, tRPC
**Go**: Gin, Fiber, Chi
**Rust**: Axum, Actix-Web

## Architecture Patterns
- Clean Architecture (DDD, Repository, Service Layer)
- Layered Architecture (Controller → Service → Repository)
- Event-Driven Architecture (Message Queue, Pub/Sub)
- CQRS (Command Query Responsibility Segregation)
- Microservices (Service Discovery, API Gateway, Circuit Breaker)

## API Standards
- RESTful API design (HATEOAS, pagination, filtering, sorting)
- GraphQL (Schema-first, resolvers, DataLoader for N+1)
- OpenAPI/Swagger documentation
- Versioning strategies (URL path, header, content negotiation)

## Authentication & Authorization
- JWT (access + refresh tokens, rotation, blacklisting)
- OAuth2 (Authorization Code, PKCE, Client Credentials)
- RBAC / ABAC (Role-Based / Attribute-Based Access Control)
- Session management (secure cookies, CSRF tokens)
- API Keys (rate limiting per key, rotation)

## Database & Storage
- **SQL**: PostgreSQL, MySQL, SQLite — indexing, migrations, connection pooling
- **NoSQL**: MongoDB (aggregation pipeline, indexing), Redis (caching, sessions, pub/sub)
- **ORM**: SQLAlchemy async, Prisma, Django ORM
- **Migrations**: Alembic, Prisma Migrate, Django migrations
- **Caching**: Redis, Memcached, in-memory (cache-aside, write-through)

## Error Handling
- Structured error responses (RFC 7807 Problem Details)
- Exception handlers / middleware per status code
- Logging (structured, request IDs, severity levels)
- Graceful degradation (circuit breakers, fallbacks, retries)

## Testing
- Unit tests (pytest, Jest, Go test)
- Integration tests (test containers, fixtures)
- API tests (supertest, httpx, Postman/Newman)
- Load tests (k6, Locust, artillery)

## Security Patterns
- Input validation (Pydantic, Zod, Joi)
- SQL injection prevention (parameterized queries)
- Rate limiting (token bucket, sliding window)
- CORS, CSP, HSTS security headers
- Secrets management (env vars, vault, .env)

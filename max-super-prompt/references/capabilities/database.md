# 🗄️ Database & Storage Capabilities

> Load trigger: Code/Architect/DevOps mode with database-related request.

## SQL Databases

| DB | Best For | Unique Features |
|---|---|---|
| PostgreSQL | Enterprise, complex queries, GIS | JSONB, full-text search, extensions (PostGIS, pgvector), partial indexes |
| MySQL / MariaDB | Web apps, LAMP stack | InnoDB, replication, partitioning |
| SQLite | Embedded, mobile, local dev | Zero-config, serverless, single file |
| CockroachDB | Distributed SQL, multi-region | Horizontal scaling, strong consistency, PostgreSQL-compatible |

## NoSQL Databases

| DB | Data Model | Best For |
|---|---|---|
| MongoDB | Document (BSON) | Flexible schema, rapid prototyping, nested data |
| Redis | Key-value | Caching, sessions, pub/sub, rate limiting, real-time leaderboards |
| DynamoDB | Key-value + document | Serverless web apps, high-scale workloads, single-digit ms latency |
| Cassandra | Wide-column | Time-series, IoT, high write throughput, multi-region |
| Neo4j | Graph | Relationships, recommendations, fraud detection, knowledge graphs |

## Performance Patterns

| Pattern | Description |
|---|---|
| Connection Pooling | Reuse connections (PgBouncer, RDS Proxy, HikariCP) |
| Index Strategy | B-tree for equality + range, GIN for JSON/array, GiST for full-text |
| Query Optimization | `EXPLAIN ANALYZE`, slow query log, missing index detection |
| Caching | Cache-aside (read: cache → DB, write: DB → invalidate cache) |
| Read Replicas | Offload reads to replicas, connection pool routes by query type |
| Partitioning | Range/list/hash partitioning for large tables, partition pruning |

## Migration Strategies

- **Zero-downtime**: Expand → Migrate → Contract pattern (online schema change)
- **Backward-compatible**: Add columns as nullable, then backfill, then enforce NOT NULL
- **Tools**: Alembic (Python), Prisma Migrate (Node.js), Flyway (Java), Sqitch (any)
- **Rollback**: Every migration must have a revert script

## ORM Best Practices

| ORM | Language | Async | Recommended For |
|---|---|---|---|
| SQLAlchemy 2.0 | Python | ✅ (async + sync) | Complex queries, legacy DBs |
| Prisma | TS/Node.js | ✅ | New projects, type safety |
| Drizzle | TS/Node.js | ✅ | Lightweight, SQL-like API |
| Diesel | Rust | ✅ | Type-safe, compile-time checked |
| GORM | Go | ❌ | Rapid development |
| EF Core | C# | ✅ | .NET ecosystem |

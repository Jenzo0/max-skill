# 🐳 DevOps Capabilities

> Load this module for deployment, infrastructure, and CI/CD tasks.
> Load trigger: DevOps Mode, or any task involving Docker, cloud, pipelines, or infrastructure.

## Containerization (Docker)
- Multi-stage builds (minimize image size)
- Docker Compose (development + production profiles)
- Health checks, restart policies, resource limits
- Docker networking (bridge, host, overlay)
- Best practices: non-root user, .dockerignore, layer caching

## Orchestration (Kubernetes)
- Pods, Deployments, StatefulSets, DaemonSets
- Services (ClusterIP, NodePort, LoadBalancer, Ingress)
- ConfigMaps + Secrets
- Helm charts (templating, dependency management)
- Horizontal Pod Autoscaling (HPA)
- Probes (liveness, readiness, startup)

## CI/CD Pipelines
- **GitHub Actions**: matrix builds, caching, environments, OIDC
- **GitLab CI**: stages, artifacts, multi-project pipelines
- **Self-hosted**: Jenkins, Drone, Woodpecker
- **Patterns**: semantic release, auto-changelog, canary deployments

## Cloud Providers
- **AWS**: EC2, ECS/EKS, RDS, S3, CloudFront, Route53, Lambda
- **GCP**: GKE, Cloud Run, Cloud SQL, Cloud Storage, Cloud CDN, Cloud Functions
- **DigitalOcean**: App Platform, Droplets, Managed Databases, Spaces

## Infrastructure as Code
- **Terraform / OpenTofu**: modules, state management, workspaces, remote backends
- **Pulumi**: infrastructure as real code (TypeScript, Python, Go)

## Monitoring & Observability
- **Metrics**: Prometheus + Grafana (dashboards, alerts, recording rules)
- **Logging**: Loki (Grafana), ELK (Elasticsearch, Logstash, Kibana)
- **Tracing**: OpenTelemetry (distributed tracing, spans, baggage)
- **Uptime**: UptimeRobot, Better Uptime, health check endpoints

## Server Management
- **Reverse Proxy**: Nginx, Caddy, Traefik (SSL termination, rate limiting, caching)
- **SSL/TLS**: Let's Encrypt (certbot, acme.sh), automatic renewal
- **Process Management**: systemd, supervisord
- **Backup**: pg_dump (PostgreSQL), restic (files), borg (dedup)
- **Firewall**: iptables, ufw, cloud security groups

## Database Operations
- Automated backups (wal-g, pg_dump cron, restic + hook)
- Migration zero-downtime strategies
- Read replicas + connection pooling (PgBouncer)
- Index management (slow query log analysis, missing index detection)

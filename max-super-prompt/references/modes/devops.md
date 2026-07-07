# 🐳 DevOps Mode

> Load trigger: Keywords matched → deploy, docker, kubernetes, k8s, ci/cd, cloud, terraform, aws, gcp, pipeline.

## Behavior

Infrastructure as Code mindset. Containers first. Security by default. Document the pipeline, not just the config.

## Output Format

```
## Infrastructure
- Services & their relationships
- Deployment topology

## Configuration
```yaml
# docker-compose / k8s / terraform
```

## Pipeline
- CI steps
- Deployment strategy
- Rollback plan
```

## Key Principles

| Principle | Practice |
|---|---|
| Immutable Infrastructure | Never modify servers — rebuild from image |
| Security by Default | Least privilege, network segmentation, secrets in vault |
| Observability | Metrics + logs + tracing from day 1 |
| Repeatability | IaC in version control, CI/CD for everything |
| Cost Awareness | Right-size resources, auto-scaling, spot instances where appropriate |

## Common Deliverables

- `Dockerfile` (multi-stage, non-root user, layer caching)
- `docker-compose.yml` (dev + prod profiles)
- Kubernetes manifests (Deployment, Service, Ingress, ConfigMap, Secret)
- Terraform modules (state management, workspaces, remote backends)
- CI pipeline (GitHub Actions / GitLab CI with caching, matrix builds, OIDC)
- Monitoring stack (Prometheus + Grafana + Loki + OpenTelemetry)

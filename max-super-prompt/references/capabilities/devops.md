# 🐳 DevOps & Infrastructure Capabilities

> Load trigger: DevOps mode, or any request involving Docker, cloud, CI/CD.

## Containerization

| Practice | Detail |
|---|---|
| Multi-stage builds | Builder stage + runtime stage — minimize image size |
| Docker Compose | Dev + prod profiles, health checks, resource limits |
| Security | Non-root user, `.dockerignore`, read-only root fs, no secrets in image |
| Networking | Bridge (default), host, overlay — choose per use case |

## Kubernetes

| Resource | Purpose |
|---|---|
| Deployment + ReplicaSet | Stateless workloads, rolling updates |
| StatefulSet | Stateful workloads (DBs, queues) with stable network identity |
| Service (ClusterIP / NodePort / LoadBalancer) | Internal/external traffic routing |
| Ingress + IngressController | HTTP routing, TLS termination, path-based routing |
| ConfigMap + Secret | Configuration and sensitive data |
| HPA (Horizontal Pod Autoscaler) | Auto-scaling based on CPU/memory/custom metrics |
| Probes (liveness, readiness, startup) | Health checking and traffic routing |

## CI/CD Patterns

| Tool | Strengths |
|---|---|
| GitHub Actions | Tight GitHub integration, matrix builds, OIDC, marketplace |
| GitLab CI | Built-in registry, multi-project pipelines, auto DevOps |
| Self-hosted (Drone, Woodpecker) | Air-gapped environments, custom infrastructure |

## IaC

| Tool | Language | State Mgmt |
|---|---|---|
| Terraform / OpenTofu | HCL | Remote backends (S3, GCS, Terraform Cloud) |
| Pulumi | TypeScript, Python, Go, C# | Managed or self-managed state |
| CDK (AWS CDK, CDKTF) | TypeScript, Python, Java | Cloud-native, construct-based |

## Observability Stack

| Pillar | Tool | Deploy |
|---|---|---|
| Metrics | Prometheus + Grafana | kube-prometheus-stack or docker-compose |
| Logs | Loki / ELK | Grafana Loki with Promtail or Fluentd |
| Tracing | OpenTelemetry | Collector + Jaeger or Tempo |
| Uptime | Health checks + alerting | Better Uptime, Grafana OnCall, PagerDuty |

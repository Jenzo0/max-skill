# 📐 Example: Designing a Real-Time Chat System

> **Mode**: Architect | **Platform**: Any

## Before Max

```
User: "Design a real-time chat system"

Chat: "Use WebSockets with a server. You could use Socket.IO or Django Channels."
```

## After Max

Max activates **Architect mode** with a full design document:

```
User: "Design a real-time chat system for 1M concurrent users"

Max: [mode: architect | score: 9 | alt: devops: 4]

🎯 Bottom Line: Event-driven microservices architecture with Redis Pub/Sub for real-time, Kafka for persistence, and horizontal scaling on Kubernetes.

🔍 Trade-offs:
┌─────────────────────────┬──────────────────────────┐
│ Option A: Monolithic    │ Option B: Microservices  │
│ + Simpler to deploy     │ + Independent scaling    │
│ - Bottleneck at 50K CCU │ + Team autonomy          │
│ - Single point of fail  │ - Higher ops complexity  │
└─────────────────────────┴──────────────────────────┘
→ Recommended: Option B for 1M CCU target

💻 Architecture:

┌──────────────┐    WebSocket     ┌───────────────┐
│  Client SDK  │ ───────────────→ │  API Gateway  │
│ (WS + Rest)  │ ←────────────── │ (Kong/Envoy)  │
└──────────────┘                  └───────┬───────┘
                                          │
                    ┌─────────────────────┼──────────────────────┐
                    ↓                     ↓                      ↓
           ┌────────────────┐   ┌────────────────┐   ┌──────────────────┐
           │  Chat Service  │   │ Message Svc    │   │  Presence Svc    │
           │  (FastAPI WS)  │   │ (Kafka Cons.)  │   │  (Redis Pub/Sub) │
           └───────┬────────┘   └───────┬────────┘   └────────┬─────────┘
                   │                    │                      │
                   ↓                    ↓                      ↓
           ┌────────────────┐   ┌────────────────┐   ┌──────────────────┐
           │ Redis Cluster  │   │  PostgreSQL   │   │   Redis Cache    │
           │ (Pub/Sub +     │   │  (Citus ext.) │   │ (User Status)    │
           │  Session Store)│   │ (Chat History)│   │                  │
           └────────────────┘   └────────────────┘   └──────────────────┘

Data Flow:
1. Client connects via WebSocket to Chat Service
2. Chat Service publishes message to Redis Pub/Sub
3. Redis fans out to all Chat Service instances → broadcasts to room
4. Message Svc consumes from Kafka for persistence in PostgreSQL
5. Presence Svc tracks online status via Redis presence channels

💾 Infrastructure:
- Kubernetes cluster (EKS/GKE) with HPA per service
- Redis Cluster (6 nodes min, 3 masters + 3 replicas)
- PostgreSQL + Citus for horizontal sharding of chat history
- Kafka for message durability and replay

✅ Next Steps:
Phase 1 (Week 1-2): Single Chat Service + Redis Pub/Sub
Phase 2 (Week 3-4): PostgreSQL persistence + Message Svc
Phase 3 (Week 5-6): Presence Svc + Horizontal scaling
Phase 4 (Week 7-8): Client SDK + Performance testing at 1M CCU
```

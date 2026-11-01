# System Design Syllabus (70 Days)

One topic per day. Each day I write notes in `notes/`, draw at least one diagram in `diagrams/`, and answer the self-test questions without looking. At the end of every week I do one full design in `designs/`.

**Rules for myself**
1. Learn the idea, then explain it in my own words in the notes.
2. Always write the *trade-offs*, not just the definition ("X is good when…, bad when…").
3. Connect each topic to something I've built (ZenWorks, ONO, Job Circle, Keva) where it fits.
4. A missed day is fine. Resume at the same day number, never skip ahead.

Tick a box when the notes are committed.

---

## Phase 1: Foundations (Days 1–7)

- [ ] **Day 1**: How to approach a design problem: requirements, scope, a repeatable framework
- [ ] **Day 2**: Back-of-envelope estimation: QPS, storage, bandwidth, latency numbers
- [ ] **Day 3**: Scalability basics: vertical vs horizontal scaling, stateless services
- [ ] **Day 4**: Availability and reliability: SLI/SLO/SLA, failure modes, redundancy
- [ ] **Day 5**: Networking essentials: DNS, TCP vs UDP, HTTP/1.1/2/3, TLS
- [ ] **Day 6**: API design: REST, gRPC, GraphQL, pagination, idempotency, versioning
- [ ] **Day 7**: Week 1 review + first mini design

## Phase 2: Core building blocks (Days 8–21)

- [ ] **Day 8**: Load balancing: L4 vs L7, algorithms, health checks
- [ ] **Day 9**: Reverse proxy and API gateway
- [ ] **Day 10**: Caching I: cache-aside, write-through, write-back, eviction policies
- [ ] **Day 11**: Caching II: Redis in depth, invalidation, stampede, hot keys
- [ ] **Day 12**: CDN and edge caching
- [ ] **Day 13**: Relational databases: indexes, B-trees, transactions, ACID, isolation levels
- [ ] **Day 14**: NoSQL families: key-value, document, wide-column, graph
- [ ] **Day 15**: SQL vs NoSQL: choosing a store and modeling data for access patterns
- [ ] **Day 16**: Replication: leader-follower, multi-leader, leaderless
- [ ] **Day 17**: Partitioning and sharding strategies
- [ ] **Day 18**: Consistent hashing
- [ ] **Day 19**: CAP, PACELC and consistency models
- [ ] **Day 20**: Message queues and pub/sub: queue vs log, RabbitMQ vs Kafka
- [ ] **Day 21**: Kafka in depth (partitions, consumer groups, offsets, delivery semantics) + Week 3 design

## Phase 3: Distributed systems (Days 22–35)

- [ ] **Day 22**: Retries, timeouts, idempotency, "exactly-once" in practice
- [ ] **Day 23**: Distributed transactions: 2PC, saga, transactional outbox
- [ ] **Day 24**: Consensus and leader election (Raft, Paxos at a conceptual level)
- [ ] **Day 25**: Distributed locks, coordination services (ZooKeeper, etcd)
- [ ] **Day 26**: Rate limiting: token bucket, leaky bucket, sliding window
- [ ] **Day 27**: Time, clocks and ordering: Lamport and vector clocks
- [ ] **Day 28**: Unique ID generation (Snowflake-style) and ordering
- [ ] **Day 29**: Probabilistic structures: Bloom filter, HyperLogLog, count-min sketch
- [ ] **Day 30**: Search: inverted index, ranking basics, Elasticsearch
- [ ] **Day 31**: Blob and file storage: S3-style design, chunking, deduplication
- [ ] **Day 32**: Resilience patterns: circuit breaker, bulkhead, backpressure, graceful degradation
- [ ] **Day 33**: Microservices: service discovery, service mesh, sidecars, when *not* to split
- [ ] **Day 34**: Event-driven design: CQRS, event sourcing
- [ ] **Day 35**: Observability: logs, metrics, traces, alerting on SLOs + Week 5 design

## Phase 4: Security, multi-tenancy, operations (Days 36–42)

- [ ] **Day 36**: Authentication and authorization: sessions, JWT, OAuth 2.0, OIDC
- [ ] **Day 37**: Multi-tenancy patterns: shared schema, schema-per-tenant, DB-per-tenant
- [ ] **Day 38**: Data security: encryption at rest and in transit, secrets management
- [ ] **Day 39**: Deployment strategies: CI/CD, blue-green, canary, feature flags
- [ ] **Day 40**: Containers and Kubernetes from a design perspective
- [ ] **Day 41**: Multi-region, geo-replication, disaster recovery, RPO/RTO
- [ ] **Day 42**: Capacity planning, cost and performance tuning + Week 6 design

## Phase 5: Classic system designs (Days 43–62)

Each design follows the same template: requirements → estimates → API → data model → high-level design → deep dive → bottlenecks and trade-offs.

- [ ] **Day 43**: URL shortener
- [ ] **Day 44**: Rate limiter as a service
- [ ] **Day 45**: Notification system (push, SMS, email)
- [ ] **Day 46**: Chat application (WhatsApp-style)
- [ ] **Day 47**: News feed / timeline
- [ ] **Day 48**: Photo sharing (Instagram-style)
- [ ] **Day 49**: Video streaming (YouTube/Netflix-style)
- [ ] **Day 50**: File sync and storage (Google Drive/Dropbox-style)
- [ ] **Day 51**: Ride matching and geospatial indexing (geohash, quadtree)
- [ ] **Day 52**: Proximity search (Yelp-style)
- [ ] **Day 53**: Typeahead / autocomplete
- [ ] **Day 54**: Web crawler
- [ ] **Day 55**: Distributed cache
- [ ] **Day 56**: Distributed message queue (a mini-Kafka)
- [ ] **Day 57**: Payments and wallet system: ledger, idempotency, reconciliation
- [ ] **Day 58**: Booking and inventory system: seat/ticket reservation, overbooking, holds (relevant to airline order and offer systems)
- [ ] **Day 59**: E-commerce and flash sale
- [ ] **Day 60**: Metrics, monitoring and log aggregation
- [ ] **Day 61**: Collaborative editing (Google Docs-style): OT vs CRDT
- [ ] **Day 62**: Multi-tenant HRMS (ZenWorks as a case study)

## Phase 6: Interview mastery (Days 63–70)

- [ ] **Day 63**: Interview structure, time management, how to drive the conversation
- [ ] **Day 64**: Trade-off language: how to justify every choice out loud
- [ ] **Day 65**: Turning my own projects (ZenWorks, ONO, Job Circle) into design stories
- [ ] **Day 66**: Mock design 1 (timed, 45 minutes)
- [ ] **Day 67**: Mock design 2
- [ ] **Day 68**: Mock design 3
- [ ] **Day 69**: Weak-spot review: redo the three weakest topics
- [ ] **Day 70**: Capstone: full written design of ZenWorks, published in `designs/`

---

## Suggested repo layout

```
system-design-journey/
├── README.md          # goal + progress tracker
├── SYLLABUS.md        # this file
├── notes/             # day-01-how-to-approach.md, day-02-estimation.md, ...
├── diagrams/          # images or Mermaid files
└── designs/           # weekly and classic full designs
```

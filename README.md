
# Concurrency & Synchronization

Mutex (Mutual Exclusion): Allows one thread at a time.
🔹 Application: Used in databases when multiple transactions update the same record.

Semaphore: Counter-based access control for multiple threads.
🔹 Application: Printer queues, allowing limited users to print at the same time.

Monitor: High-level concurrency construct (wraps mutex + condition).
🔹 Application: Java synchronized methods to control thread access.

Deadlock: Circular wait with no progress.
🔹 Application: Two ATMs trying to lock user accounts in different order.

Livelock: Threads keep working but no progress.
🔹 Application: Two cars keep reversing to give way but still block each other.

Starvation: Low-priority thread never gets CPU.
🔹 Application: Background tasks on busy servers.

Race Condition: Simultaneous access to shared data causes errors.
🔹 Application: Online ticket booking showing 2 people the last seat.

Producer-Consumer Problem: Coordination between producer (data creator) and consumer (data user).
🔹 Application: Buffer in YouTube – producer loads data, consumer plays it.



---

# Communication & Messaging

Pub-Sub (Publish-Subscribe): Publisher sends messages to topic, subscribers consume.
🔹 Application: Stock price updates to millions of clients in real-time.

Message Queue (MQ): Stores messages until consumed.
🔹 Application: Order processing in Amazon (RabbitMQ, Kafka).

Event Bus: Central channel for events.
🔹 Application: Frontend apps broadcasting state changes across components.

Point-to-Point Messaging: Direct one-to-one communication.
🔹 Application: Email delivery from one sender to one inbox.

Event-driven Architecture: React to triggers asynchronously.
🔹 Application: Payment gateway confirming order after transaction success.



---

# Scalability & Load Handling

Load Balancer (LB): Distributes traffic across servers.
🔹 Application: Google search requests balanced across thousands of servers.

Horizontal Scaling: Adding more machines.
🔹 Application: Netflix adding more servers during peak hours.

Vertical Scaling: Adding CPU/RAM to a server.
🔹 Application: Upgrading database server to handle larger queries.

Rate Limiting: Restricting requests per client.
🔹 Application: Twitter API allows limited tweets per minute.

Backpressure: Slow consumer forces producer to slow down.
🔹 Application: Streaming services pause buffering when network slows.

Content Delivery Network (CDN): Cache static content globally.
🔹 Application: Cloudflare serving cached website images/videos closer to users.



---

# Storage & Databases

Relational DB (SQL): Structured schema + ACID.
🔹 Application: Banking systems requiring strict transactions.

NoSQL DB: Schema-less.
🔹 Application: Instagram storing flexible JSON posts with images, comments.

Sharding: Splitting data across servers.
🔹 Application: Twitter user IDs split across shards for fast lookups.

Replication: Copying data for reliability.
🔹 Application: Facebook replicating databases across continents.

CAP Theorem: Consistency, Availability, Partition Tolerance.
🔹 Application: Cassandra prefers availability + partition tolerance.

Strong Consistency: All reads return the latest write.
🔹 Application: Bank balance check after transfer.

Eventual Consistency: Data syncs later.
🔹 Application: Amazon product stock showing “X left in stock” updates slightly later.



---

# Caching

Cache (in-memory store): Faster reads.
🔹 Application: Redis caching user sessions in e-commerce websites.

Write-through Cache: Write to cache + DB.
🔹 Application: Shopping cart system updating cache and DB instantly.

Write-back Cache: Write to cache, sync later.
🔹 Application: CPU caching instructions before committing to memory.

Eviction Policies: LRU, LFU, FIFO.
🔹 Application: Web browser discarding least recently visited pages.

Cache Invalidation: Update/remove stale data.
🔹 Application: Instagram updating like counts after new likes.



---

# System Architecture Patterns

Monolithic Architecture: One codebase + one deploy.
🔹 Application: Early-stage startups.

Microservices: Small services communicating via APIs.
🔹 Application: Netflix – separate services for recommendations, billing, streaming.

Service-Oriented Architecture (SOA): Reusable services.
🔹 Application: Enterprise systems like ERP software.

CQRS: Split read & write models.
🔹 Application: Banking apps – transactions vs. account summary queries.

Event Sourcing: State = sequence of events.
🔹 Application: Git version control maintains history of commits.



---

# Reliability & Fault Tolerance

Failover: Switch to backup system.
🔹 Application: Backup power servers in AWS.

Consensus Protocols (Raft/Paxos): Agreement in distributed systems.
🔹 Application: Kubernetes ensuring leader node election.

Quorum: Minimum nodes agreeing.
🔹 Application: Cassandra requiring majority read/write nodes.

Circuit Breaker: Stops calling failing service temporarily.
🔹 Application: Netflix Hystrix preventing cascading failures.

Idempotency: Multiple retries = same effect.
🔹 Application: Payment APIs ensuring double debit doesn’t occur.



---

# Networking & APIs

REST API: Resource-based, stateless.
🔹 Application: GitHub APIs for repos and issues.

GraphQL: Query-specific data.
🔹 Application: Facebook apps fetching only required post/user data.

gRPC: Binary protocol, faster than JSON.
🔹 Application: Google microservices inter-communication.

WebSockets: Persistent 2-way connection.
🔹 Application: WhatsApp web for live messaging.

API Gateway: Unified entry for APIs.
🔹 Application: AWS API Gateway for authentication + rate limiting.

Reverse Proxy: Forwards requests.
🔹 Application: Nginx serving web traffic for multiple apps.



---

# Monitoring & Logging

Logs: Records of system activity.
🔹 Application: Error logs in production servers.

Metrics: Quantitative performance data.
🔹 Application: Tracking request latency in Prometheus.

Tracing: Request journey across microservices.
🔹 Application: Jaeger showing root cause of slow transactions.

Health Checks: Monitoring service availability.
🔹 Application: Kubernetes probes restarting failed containers.



---

# Other Essential Keywords

Throughput: Work done per second.
🔹 Application: Amazon handles millions of orders/sec.

Latency: Delay per request.
🔹 Application: Google aims <100 ms search response.

Availability: % uptime.
🔹 Application: AWS promises 99.99% uptime SLAs.

Durability: Data persistence after failure.
🔹 Application: Gmail never losing emails even after server crashes.

Data Partitioning: Splitting large datasets.
🔹 Application: YouTube videos split across regions.

Bloom Filter: Probabilistic data structure for membership check.
🔹 Application: Gmail detecting if email address already exists.

Consistent Hashing: Even distribution across servers.
🔹 Application: DynamoDB storing key-value pairs reliably.



---

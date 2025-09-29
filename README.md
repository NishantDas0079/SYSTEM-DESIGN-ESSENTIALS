
# Concurrency & Synchronization

Mutex (Mutual Exclusion): Ensures only one thread/process accesses a shared resource.

DB Transactions: Prevents two people withdrawing the same balance.

File Systems: Prevents two apps writing to a file simultaneously.

OS Kernel: Controls process scheduling safely.


Semaphore: Controls access to resources by multiple threads.

Database Connection Pooling.

Traffic Lights: Multiple cars can cross, but max limit is set.

Producer-Consumer Buffers: Multiple consumers access queue.


Monitor (High-level Lock + Condition Variables):

Java synchronized blocks.

C# lock statements.

Thread-safe bounded buffers.


Deadlock: Circular wait with no progress.

ATM machines locking user accounts differently.

Dining Philosophers Problem (classic example).

Two microservices calling each other waiting forever.


Livelock: Processes keep changing states but no progress.

Two robots trying to avoid collision but keep dodging.

Network retries flooding requests but never succeeding.

Multiplayer games where characters keep blocking each other.


Starvation: Some processes never get resources.

Low-priority jobs in OS scheduling.

Background apps on mobile rarely executed.

Database queries blocked by heavy long queries.


Race Condition: Multiple threads cause inconsistent state.

Bank transfer double deduction.

Online voting system counting one vote multiple times.

Airline booking same seat for two passengers.


Producer-Consumer Problem: Balance between producer speed and consumer speed.

YouTube streaming buffer.

Logging systems (producer = app, consumer = log writer).

Kafka topics – producers push events, consumers process.




---

# Communication & Messaging

Publish-Subscribe (Pub-Sub): One-to-many messaging.

Stock market live feeds.

YouTube notifications when channel uploads.

Uber – rider and driver both get updates.


Message Queue (MQ): Stores messages until consumed.

Amazon order fulfillment pipeline.

Food delivery apps processing orders.

Banking systems ensuring transactions are queued safely.


Event Bus: Central stream for events.

Frontend apps broadcasting login/logout events.

IoT sensors sending readings to a hub.

Slack chat events routed across services.


Point-to-Point Messaging: One producer → one consumer.

Email delivery.

SMS messages.

Peer-to-peer file transfer.


Event-driven Architecture: Components trigger actions on events.

Payment success triggers invoice generation.

IoT door sensor triggers home alarm.

AWS Lambda functions running on S3 file uploads.




---

# Scalability & Load Handling

Load Balancer (LB): Distributes traffic.

Google Search traffic split across servers.

YouTube video streaming distributed worldwide.

E-commerce websites during sales (Flipkart Big Billion Day).


Horizontal Scaling: Add more machines.

Netflix adding servers during peak hours.

Gaming servers handling tournaments.

WhatsApp expanding chat servers with more users.


Vertical Scaling: Add more power to one machine.

Upgrading SQL DB to bigger RAM/CPU.

Enterprise ERP servers running on heavy machines.

Legacy systems scaling by hardware upgrades.


Rate Limiting: Restrict client request rate.

Twitter API limiting posts per min.

Login attempts restricted to avoid brute force.

Cloudflare limiting requests to prevent DDoS.


Backpressure: Slow consumers throttle producers.

Netflix pauses buffering if consumer device is slow.

Kafka consumers lag behind, producers throttle.

Printer queue slowing print requests.


Content Delivery Network (CDN): Cache content close to users.

Cloudflare, Akamai serving cached websites.

Netflix caching videos regionally.

Facebook caching images across data centers.




---

# Storage & Databases

Relational DB (SQL): ACID transactions, structured.

Banking systems.

ERP software.

E-commerce product catalog with strict schema.


NoSQL DB: Schema-less, flexible.

Instagram storing user posts.

MongoDB storing JSON-based chat messages.

Cassandra storing logs and IoT data.


Sharding: Split large dataset into partitions.

Twitter splitting users across shards.

YouTube storing videos across multiple servers.

E-commerce splitting orders by region.


Replication: Copies of DB across servers.

Facebook DB replicated across continents.

Gmail keeping copies of emails across data centers.

Stock exchanges replicating trade data in real-time.


CAP Theorem: Pick any 2 (C, A, P).

Cassandra: AP.

MongoDB: CP.

RDBMS: CA.


Strong Consistency: All reads see latest data.

Bank account balance check.

Stock trading systems.

Hospital medical records updates.


Eventual Consistency: Updates propagate later.

Amazon inventory status.

DNS propagation.

Social media likes showing delayed.




---

# Caching

Cache: Faster storage for hot data.

Redis caching user sessions.

CDN caching web assets.

CPU caching frequently used instructions.


Write-through Cache: Write to cache + DB simultaneously.

Shopping cart updates.

Game leaderboard scores.

E-commerce price updates.


Write-back Cache: Write to cache, sync later.

CPU write-back caches.

File system write caching.

Game state updates synced periodically.


Eviction Policies: LRU, LFU, FIFO.

Browser discarding old tabs.

Redis evicting least used keys.

OS memory page replacement.


Cache Invalidation: Removing outdated entries.

Instagram like counter update.

Cloudflare purging CDN cache.

News sites updating headlines.




---

# System Architecture Patterns

Monolithic Architecture: One unit.

Early Facebook.

University ERP software.

Startups MVP apps.


Microservices: Small, independent services.

Netflix recommendations, billing, search.

Amazon order, payment, delivery services.

Spotify playlist & playback microservices.


SOA (Service-Oriented Architecture): Larger services.

Banking core services.

Government IT systems.

Airline booking systems.


CQRS: Split reads/writes.

Bank transaction processing.

E-commerce order status vs checkout.

Healthcare patient data vs new entries.


Event Sourcing: Store events as source of truth.

Git commits.

Blockchain transaction history.

E-commerce order lifecycle.




---

# Reliability & Fault Tolerance

Failover: Backup system kicks in.

AWS regions switch during outage.

Banking DR sites.

Telecom tower failover.


Consensus Protocols (Raft/Paxos): Agreement in distributed systems.

Kubernetes leader election.

Blockchain consensus.

ZooKeeper coordination.


Quorum: Minimum votes needed.

Cassandra writes need majority nodes.

Blockchain transactions confirmed after quorum.

Distributed voting systems.


Circuit Breaker: Stop repeated failures.

Netflix Hystrix.

Payment API fallback.

Microservices avoiding cascading failures.


Idempotency: Same request safe to retry.

Payment systems avoiding double charge.

Email confirmation links.

REST APIs safe retry of PUT requests.




---

# Networking & APIs

REST API: Stateless, resource-based.

GitHub API.

Twitter API.

Weather forecast APIs.


GraphQL: Query only required data.

Facebook feed API.

Shopify storefront API.

GitHub GraphQL API.


gRPC: Binary, efficient.

Google microservices.

High-speed financial systems.

IoT devices sending telemetry.


WebSockets: Full-duplex real-time connection.

WhatsApp Web.

Online multiplayer games.

Stock ticker live updates.


API Gateway: Entry for routing/auth.

AWS API Gateway.

Netflix Zuul.

Kong API Gateway.


Reverse Proxy: Forward requests.

Nginx load balancing.

Cloudflare proxy for security.

Apache reverse proxy for backend.




---

# Monitoring & Logging

Logs: Track activities.

Application error logs.

System event logs.

Security audit logs.


Metrics: Quantitative monitoring.

CPU usage tracking.

Latency stats in Prometheus.

E-commerce site order per second.


Tracing: Track request across systems.

Jaeger traces.

Zipkin distributed tracing.

APM tools like Datadog.


Health Checks: Service availability tests.

Kubernetes liveness probes.

Load balancer health checks.

Microservices readiness probes.




---

# Other Important Keywords

Throughput: Requests per sec.

Amazon millions/sec.

Stock exchanges trades/sec.

Payment gateways transactions/sec.


Latency: Delay in processing.

Google <100 ms search.

Zoom <50 ms voice delay.

Video games <20 ms input delay.


Availability: Uptime percentage.

AWS SLA 99.99%.

Netflix global uptime.

Bank ATMs 24/7 availability.


Durability: Data remains safe.

Gmail never losing emails.

Blockchain transactions permanent.

Cloud storage (S3) 11 nines durability.


Bloom Filter: Probabilistic membership test.

Gmail checking duplicate addresses.

Databases filtering cache misses.

CDNs checking cached objects.


Consistent Hashing: Even key distribution.

DynamoDB partitioning.

CDN content placement.

Load balancer routing users to servers.




---





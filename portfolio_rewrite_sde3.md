# 1. HERO SECTION (Above the fold)

**Headline:** Architecting High-Performance Distributed Systems at Scale
**Sub-headline:** Senior Backend Engineer · SDE3 · Distributed Systems & Microservices
**Tags/Metrics Line:** Delivering mission-critical fault-tolerant platforms. Impact includes migrating 50TB+ databases with zero downtime and building real-time pipelines processing 100K+ writes/sec.
**Current Role & Background:** Java · Spring Boot · AWS · Kafka · OpenShift

---

# 2. ABOUT SECTION

Senior Backend Engineer with 6+ years of experience architecting and scaling distributed systems across fintech and enterprise domains. I specialize in designing fault-tolerant microservices, optimizing database performance, and driving complex system migrations gracefully. 

Driven by operational excellence, I have successfully migrated a 50TB graph database out of a legacy on-prem monolith and architected data pipelines capable of ingesting 100K+ writes/sec cleanly. My approach balances deep academic rigor in distribute systems theory with pragmatic, maintainable, and highly observable engineering. I build systems that hold up under pressure.

---

# 3. EXPERIENCE 

### Chief Engineer / Lead Software Engineer
*Samsung Electronics & Western Union*

**The Problem:** Existing infrastructure struggled with the latency, consistency, and scale demands of real-time financial use cases, particularly across lending and transaction fraud detection in global markets.
**The Solution:** Architected event-driven microservices architectures utilizing Kafka and Flink with exactly-once semantics and robust idempotency patterns for financial correctness.
**The Impact:** Designed and owned pipelines processing over **100M events/day** with **sub-second latency**. Eliminated manual reconciliation flows to achieve near real-time settlement while handling **100K+ writes/sec**.

### Software Engineer 3
*Cisco*

**The Problem:** A monolithic legacy system hampered deployment velocity and could no longer handle explosive data growth, while the primary 50TB Neo4j graph database became a major operational bottleneck and financial liability.
**The Solution:** Led a phased Strangler Fig migration to decouple the monolith into Spring Boot and AWS ECS microservices. Engineered and executed a seamless database migration to Amazon Neptune with full Gremlin traversal parity.
**The Impact:** Delivered **~$150K in annual infrastructure cost savings** with **zero downtime** and no regression in query latency. Decoupled teams, unlocking independent CI/CD delivery pipelines.

### Software Engineer 2
*Cisco*

**The Problem:** Financial partner onboarding was blocked by an inefficient, monolithic configuration import process that frequently timed out and failed partially under load.
**The Solution:** Redesigned the data-ingestion pipeline leveraging asynchronous processing, bulk-insert optimizations, and robust dead-letter queues. 
**The Impact:** Engineered a bulk import system capable of reliably processing **10K+ complex hierarchical records in seconds**, eliminating manual debugging and saving hundreds of engineering hours per quarter. Optimized graph queries for a **40% faster response time** at scale.

---

# 4. SYSTEM DESIGN (NEW)

### Architectural & System Design Portfolio
*A spotlight on architectural patterns and distributed systems behavior.*

* **Real-time Fraud Detection Pipeline:** Designed an event-streaming topology using Kafka and Flink. Addressed partial failures and message duplication using dual-write patterns and idempotent message processors to maintain high availability under massive traffic spikes.
* **Planet-Scale Notification Platform:** Architected a globally distributed publish-subscribe system with strict delivery guarantees. Implemented rate-limiting, backpressure, and priority queuing to handle diverse SLA requirements across different notification tiers.
* **Distributed Financial Ledger:** Enforced strong consistency in a distributed datastore. Built a resilient payment orchestration engine using the Saga pattern for managing long-running transaction states, resolving distributed transactions safely across microservices.

---

# 5. CASE STUDY (DEEP DIVE)

### Monolith to Microservices & 50TB Database Migration

**The Challenge:**
At Cisco, a core platform service serving global enterprise customers operated as a tightly coupled monolith backed by an expensive, on-prem 50TB Neo4j graph database. As transaction volume grew aggressively, releasing new features became brittle, and database licensing and operational costs ballooned out of control.

**Design Decisions & Architecture:**
1. **The Strangler Fig Pattern:** I spearheaded the incremental decomposition of the monolith, routing read traffic to new Spring Boot microservices deployed on AWS ECS via an API Gateway.
2. **Database Migration Strategy:** To move off Neo4j to Amazon Neptune, we required absolute zero downtime. We implemented a dual-write mechanism, keeping the legacy database as the source of truth while passively syncing to the new Neptune cluster.
3. **Query Engine Parity:** Abstracted the graph querying logic to ensure new services executed Gremlin traversals efficiently without tying business logic strictly to the underlying database implementation.

**Trade-offs Evaluated:**
* *Strong vs. Eventual Consistency:* Opted for eventual consistency heavily buffered by Kafka for data replication, favoring 99.99% availability of the entitlement APIs over strict linearizability during the migration window.
* *Dual-Write Complexity:* Accepted higher short-term architectural complexity to guarantee a safe, instantaneous rollback path if performance severely degraded in the new datastore under production load.

**The Impact:**
The migration was completed with **zero downtime**. We slashed infrastructure and licensing costs by **~$150K annually**, improved fault isolation dramatically, and slashed average query latency at the 99th percentile by 40%.

---

# 6. TECH STACK 

* **Languages:** Java, SQL, Python
* **Backend & Frameworks:** Spring Boot, REST APIs, Microservices Architecture
* **Cloud & Infrastructure:** AWS (ECS, S3, RDS), Docker, OpenShift, Jenkins CI/CD
* **Data Storage & Streaming:** Apache Kafka, Apache Flink, Amazon Neptune (Gremlin), Neo4j, MongoDB
* **Observability:** ELK Stack, Prometheus, Grafana

---

# 7. DESIGN IMPROVEMENTS (TEXTUAL GUIDANCE)

* **Visual Hierarchy:** Make your metrics and impact numbers ("50TB Database", "100K writes/sec") visually pop using your brand's accent color rather than just bold text. Hiring managers scan for numbers first.
* **Section Spacing:** Increase padding between your case study and the rest of the experience. The system design and case study sections are high-signal and need generous whitespace so they don't get lost in a wall of text.
* **Highlighting Metrics:** Use high-contrast callout boxes or a distinct 2-column layout for your core metrics to immediately draw the eye when someone opens the page.
* **CTA Buttons:** Refine the hero CTAs. Instead of an ambiguous "View Resume", try "**Download Resume**" in a solid primary button, paired with "**Read 50TB Migration Case Study**" as a secondary outline button. Move Contact/GitHub underneath to guide eyes directly to your highest-value content.

---

# 8. REMOVED LOW SIGNAL CONTENT (Notes)

* Removed generic bullet points about "using JUnit to increase test coverage" and basic CI/CD integrations from the internship and SE2 roles. While valuable, they distract a senior hiring manager from your massive architectural achievements like the 50TB database migration.
* Condensed standard software engineering responsibilities ("mentored junior engineers", "delivered feature enhancements") into the background. The rewritten copy aggressively focuses on system architecture, data scale, and concrete bottom-line impact.

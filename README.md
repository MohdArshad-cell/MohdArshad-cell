<div align="center">
  <h1>⚡ MOHD ARSHAD</h1>
  <p><strong>Distributed Systems & High-Concurrency Backend Engineer</strong></p>
  <p><em>Engineering fault-tolerant financial pipelines, distributed consensus mechanisms, and sub-15ms embedded JVM intelligence.</em></p>

  <p>
    <a href="https://linkedin.com/in/mohd-arshad-156227314"><img src="https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white" /></a>
    <a href="mailto:arshadmohd8574@gmail.com"><img src="https://img.shields.io/badge/Email-D14836?style=for-the-badge&logo=gmail&logoColor=white" /></a>
    <a href="https://portfolio-2-0-sigma-gray.vercel.app/"><img src="https://img.shields.io/badge/Live_Portfolio-00F3FF?style=for-the-badge&logo=vercel&logoColor=black" /></a>
    <img src="https://img.shields.io/badge/TCS-Incoming_Systems_Engineer-emerald?style=for-the-badge&logo=tata&logoColor=white" />
  </p>
</div>

---

### 📊 SYSTEM TELEMETRY & CAPABILITIES AT A GLANCE

```text
┌─────────────────────────┬──────────────────────────┬─────────────────────────┐
│     PEAK THROUGHPUT     │    FRAUD INFERENCE p99   │   TRANSACTION MODEL     │
│       10,000+ RPS       │         < 15 ms          │   Double-Entry (ACID)   │
├─────────────────────────┼──────────────────────────┼─────────────────────────┤
│    CONCURRENCY LOCK     │    STREAM RELIABILITY    │    RECOVERY PROTOCOL    │
│  Redis Redlock + Lua    │   Kafka DLQ + 0% Loss    │   Saga Orchestration    │
└─────────────────────────┴──────────────────────────┴─────────────────────────┘

```
### 🏗️ CORE ENGINEERING FOUNDATIONS

#### 01. Distributed Concurrency & Transactions

* **Distributed Mutex & Race Condition Mitigation:** Designing atomic multi-resource locking using **Redis Redlock** algorithms and in-memory Lua scripts to eliminate overselling and balance corruption under severe concurrent contention.


* **Eventual Consistency & Rollbacks:** Implementing the **Saga Orchestration Pattern** backed by a **Transactional Outbox Table** to guarantee dual-write consistency and automated compensating reversals across independent microservices.


* **Strict Accounting Invariants:** Enforcing append-only double-entry ledger bookkeeping where balance mutations strictly follow:

$$\text{Balance}_{\text{final}} = \text{Balance}_{\text{initial}} + \sum(\text{Credits}) - \sum(\text{Debits})$$



blocking direct `UPDATE` / `DELETE` statements at the database schema layer.



#### 02. Asynchronous Messaging & Fault Tolerance

* **Partition Strategy & Key Hashing:** Architecting high-throughput **Apache Kafka** event fabrics with custom partition hash routing to preserve absolute message ordering per account entity.
* **Transient Failure Isolation:** Configuring resilient multi-stage retry loops with **Dead Letter Queues (DLQ)**, exponential backoff, and randomized jitter to isolate downstream provider outages.
* **Resilience Primitives:** Protecting internal APIs with **Resilience4j** circuit breakers, bulkhead thread isolation, and sliding-window rate limiters.

#### 03. Low-Latency Machine Intelligence & Research

* **JVM-Native Embedded Inference:** Executing pre-trained machine learning models (XGBoost) natively inside Java microservices via **ONNX Runtime**, bypassing network RPC overhead to slash fraud scoring down to sub-15ms.


* **Statistical Lead-Lag Modeling:** Applying **Granger Causality** time-series tests and **PCA** dimensionality reduction on NLP transformer outputs (DistilBERT) for predictive conflict modeling.
* **Asynchronous LLM Orchestration:** Designing non-blocking reactive pipelines that couple Spring Boot cores with Python AI workers for automated document compilation.

---

### 🚀 FLAGSHIP DISTRIBUTED SYSTEMS ARCHITECTURES

#### 1. [SentinelLedger](https://www.google.com/search?q=https://github.com/MohdArshad-cell/SentinelLedger) — Distributed Financial Ledger & Payment Engine

> High-throughput financial ledger engine handling 10,000+ RPS with double-entry accounting, distributed locking, and native in-memory fraud scoring.
> 
> 

```text
[ Client Request ] ──► [ API Gateway ] ──► [ Payment Orchestrator ]
                                                    │
                 ┌──────────────────────────────────┴──────────────────────────────────┐
                 ▼                                                                     ▼
     [ Redis Redlock / Idempotency ]                                   [ ONNX Runtime (Embedded ML) ]
     (Exclusive Mutex Lock)[cite: 1]                                            (< 15ms In-Memory Fraud Score)[cite: 1]
                 │                                                                     │
                 └──────────────────────────────────┬──────────────────────────────────┘
                                                    ▼
                                    [ Apache Kafka Event Backbone ]
                                                    │
                 ┌──────────────────────────────────┴──────────────────────────────────┐
                 ▼                                                                     ▼
     [ Ledger Engine (PostgreSQL) ]                                       [ Wallet Read Service ]
     (Append-Only Double-Entry Table)[cite: 1]                                   (CQRS Balance Projection)[cite: 1]
                 │
     [ Transactional Outbox ] ──► (Guaranteed At-Least-Once Replay)[cite: 1]

```

* **Core Tech:** Java 21, Spring Boot 3, Apache Kafka, PostgreSQL (ACID), Redis Redlock, ONNX Runtime, Kubernetes (HPA)



---

#### 2. [FlashTix](https://github.com/MohdArshad-cell/FlashTix-Backend) — High-Concurrency Ticketing Engine

> *High-surge ticketing platform sustaining 5,000+ RPS with zero overselling anomalies via Redis atomic operations and database fail-safe locking.*

```text
[ 5k+ Concurrent Users ] ──► [ Spring Boot Cluster ] ──► [ Redis Lua Script Engine ]
                                                                │  (Atomic Fast-Path Decrement)
                                                                ▼
                                                    [ PostgreSQL DB (@Version) ]
                                                    (Optimistic Locking Fail-Safe Boundary)

```

* **Core Tech:** Java 21, Spring Boot 3, Redis (Lua/Redlock), PostgreSQL, HikariCP, Prometheus, Grafana

---

#### 3. [StreamFlow](https://github.com/MohdArshad-cell/StreamFlow-Backend) — Distributed Event Streaming Fabric

> *Horizontally scalable notification orchestrator processing 10,000+ events/sec with automated fault recovery and write-through caching.*

```text
[ Upstream Publishers ] ──► [ Kafka Topic Partitions ] ──► [ Consumer Worker Cluster ]
                                                                   │
                         ┌─────────────────────────────────────────┴──────────────────────────┐
                         ▼                                                                    ▼
             [ Redis Write-Through Cache ]                                        [ DLQ Exponential Retry ]
             (Sub-5ms Read Latency)                                               (Isolates Downstream Outages)

```

* **Core Tech:** Java, Spring Boot, Apache Kafka, Redis, MongoDB, Zipkin Distributed Tracing, Docker

---

#### 4. [GeoSentinel](https://github.com/mohdarshad-cell/GeoSentinal) — Computational Conflict Simulation Engine

> *Synthetic simulation framework statistically validating predictive links between narrative sentiment and kinetic escalation.*

* **Core Tech:** Python, DistilBERT Transformers, Principal Component Analysis (PCA), Granger Causality Statistics

---

### 🛠️ TECHNICAL ARSENAL

| Domain | Production Tooling & Protocols |
| :--- | :--- |
| **Languages** | Java 21 (Virtual Threads), Python, SQL (PostgreSQL), TypeScript |
| **Distributed Systems** | Spring Boot 3, Apache Kafka, Redis (Redlock, Lua, Caching), Saga Pattern, Transactional Outbox, gRPC, REST[cite: 1] |
| **Databases & Storage** | PostgreSQL (Append-Only Ledger, Index Tuning, HikariCP), MongoDB, Redis[cite: 1] |
| **Resilience & Telemetry** | Resilience4j, Prometheus, Grafana, Distributed Tracing (Zipkin/OpenTelemetry), Testcontainers |
| **AI & Computational** | ONNX Runtime (JVM), Spring AI, Google Gemini API, DistilBERT, Scikit-learn[cite: 1] |
| **Cloud & Infrastructure** | Docker Multi-Stage, Kubernetes (HPA scaling on Kafka lag), Linux/Bash, GitHub Actions CI/CD[cite: 1] |

---

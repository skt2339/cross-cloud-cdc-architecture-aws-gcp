# Cross-Cloud Near Real-Time CDC Data Platform (AWS → GCP)

## 1. High-Level Architecture

Aurora → AWS DMS → MSK (Kafka)

Cross-cloud replication via Kafka MirrorMaker 2

GCP Pub/Sub → Dataflow → BigQuery

Designed for ≤5 min SLA and fault isolation

## 2. CDC Ingestion Approach

Log-based CDC using Aurora binlogs / WAL

Exactly-once semantics via Kafka offsets

Supports inserts, updates, deletes

Schema evolution handled via schema registry

## 3. Cross-Cloud Data Movement & Reliability

Encrypted Kafka replication (TLS)

Offset-based replay for recovery

Idempotent writes in BigQuery

Ordering preserved per primary key

## 4. Data Layering & Modeling

Raw CDC (append-only)

Cleaned/validated layer

Fact tables for analytics

Downstream propagation on change

## 5. Snapshots & Historical Analysis

7-day rolling snapshot

Monthly snapshot tables

Partitioned by date for cost efficiency

## 6. Backfills & Data Hole Recovery

Offset rewind from Kafka

Time-bounded reprocessing

Safe recomputation without duplication

## 7. Accuracy, Reconciliation & Auto-Healing

Row counts & checksum comparison

Lag-based alerts

Auto-retry and replay pipelines

## 8. Cost Optimization & Trade-offs

BigQuery partitioning & clustering

Streaming vs micro-batch trade-offs

Storage lifecycle policies

## 9. Failure Scenarios & Design Decisions

Kafka outage → replay

GCP outage → backlog buffering

Schema breaking changes → quarantine


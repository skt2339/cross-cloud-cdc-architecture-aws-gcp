# CDC Ingestion Strategy

### Source
- Amazon Aurora MySQL & PostgreSQL
- High write volume
- Schema evolution expected

### CDC Capture
- Debezium or AWS DMS captures:
  - Inserts
  - Updates
  - Deletes
- Each event includes:
  - Primary key
  - Operation type
  - Commit timestamp
  - Before/after images

### Streaming Layer
- AWS MSK (Kafka) used for:
  - Ordering guarantees per key
  - Replayability
  - Backpressure handling

### Cross-Cloud Transfer
- Kafka Connect pushes CDC events to GCS
- Secure transfer using:
  - IAM roles
  - Service accounts
  - TLS encryption

### SLA
- End-to-end latency ≤ 5 minutes
- Streaming-first, no batch dependency

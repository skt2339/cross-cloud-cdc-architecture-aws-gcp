# Assumptions & Trade-offs

### Assumptions
- Near real-time analytics is business critical
- Slight delay acceptable over incorrect data
- Kafka expertise exists on AWS side

### Trade-offs
- Kafka chosen over batch pipelines for correctness
- BigQuery chosen for analytical scale
- Raw CDC retained longer for recovery at higher storage cost

### Why This Works
- Strong ordering guarantees
- Clear separation of concerns
- Scales with data volume and schema changes

# Cost Optimization Strategy

### Storage
- Partitioned BigQuery tables by event date
- Raw CDC data retained with TTL policies

### Query Optimization
- Use clustered tables for fact queries
- Avoid SELECT *
- Pre-aggregated snapshot tables

### Streaming Cost Control
- Batch CDC events in micro-windows
- Tune Kafka retention to minimum required

### Trade-off
- Slightly higher streaming cost accepted
- Significant reduction in recomputation and reprocessing cost

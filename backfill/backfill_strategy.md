# Backfills & Data Recovery

### Scenarios Handled
- Missed CDC events
- Late-arriving data
- Historical corrections

### Strategy
- Kafka offsets allow replay from any point
- Raw CDC layer acts as source of truth
- Backfills reprocess data into downstream layers

### Safety
- Idempotent writes using primary keys
- Partition-based reprocessing
- No direct writes to fact tables during backfill

### Consistency
- Downstream layers recomputed deterministically
- Snapshots regenerated after backfill

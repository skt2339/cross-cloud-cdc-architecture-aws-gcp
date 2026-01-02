# High-Level Architecture Overview

This platform enables near real-time analytics (≤5 minutes SLA) by capturing
change data from Amazon Aurora databases in AWS and delivering it reliably
to Google BigQuery for analytics.

The design focuses on:
- CDC correctness (insert/update/delete)
- Cross-cloud reliability
- Schema evolution safety
- Cost-aware scaling

### Flow Summary

1. Aurora MySQL / PostgreSQL generate CDC events
2. AWS MSK (Kafka) streams ordered CDC records
3. Kafka Connect pushes events securely to GCP
4. Raw CDC data lands in BigQuery
5. Layered transformations produce analytics-ready facts
6. Monitoring + reconciliation ensure correctness

This design avoids batch-heavy pipelines and supports replay, recovery,
and historical reconstruction.

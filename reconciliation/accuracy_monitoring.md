# Accuracy, Reconciliation & Monitoring

### Reconciliation
- Row count comparison:
  - Source Aurora vs BigQuery facts
- Checksum-based validation for critical tables
- Delete counts tracked explicitly

### Monitoring
- Kafka lag monitoring
- BigQuery ingestion delay metrics
- Data freshness alerts

### Auto-Healing
- Failed consumers auto-restart
- Replay from last committed offset
- Alerts trigger manual intervention if SLA breached

# Architecture Diagram (Textual)

[Aurora MySQL / PostgreSQL]
        |
        | (binlog / WAL)
        v
[AWS DMS / Debezium]
        |
        v
[AWS MSK (Kafka)]
        |
        | (secure cross-cloud transfer)
        v
[Kafka Connect → GCS Sink]
        |
        v
[GCS Landing Zone]
        |
        v
[BigQuery Raw CDC Tables]
        |
        v
[Cleaned / Validated Tables]
        |
        v
[Fact Tables + Snapshots]

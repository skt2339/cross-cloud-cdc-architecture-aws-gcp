<img width="839" height="245" alt="Screenshot 2026-01-02 at 10 19 10 AM" src="https://github.com/user-attachments/assets/6042696a-092e-486d-867b-c451490b0f45" />





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

# The Data Engineering Lifecycle
- Due to the increased level of abstraction, DEs have become data lifecycle engineers
- Storage occures throughout the lifecycle as data flows from the beginning to the end (cornerstone)
- Undercurrents: Security, data management, DataOps, data architecture, orchestration, software engineering.
## Generation (Source Systems)
- The DE needs to have a working understanding of the way source systems work: **the way they generate data, the frequency, velocity and variety of the data.**
- This is the stage that is generally out of your control, therefore, a lot of errors migh occur here if not properly handled.
- Considerations:
    - Type of source (App, Iot)
    - Data persistance: How long?
    - Data generation rate
    - Data consistency: Errors, duplicates, order
    - Data being pulled: Multiple events, tables, etc.
    - Communication between producers and consumers: Contracts?
    - Snapshots vs CDC: This influences how are we going to handle deduplication
    - Reading impact: Is it impacted if I read directly from PROD?
## Storage
- Storage is the most complicated choice: Too many offers in the market, few solutions are purelty storage, storage is the cornerstone of the cycle.
- Considerations:
    - Read/write speeds
    - Understanding how the storage system works
    - Scaling considerations: Size / Operation rate / Write volume
    - Schema agnostic / Flexible / Schema enforced
    - Regulatory compliance
    - Data temperature considerations: How often data will be consumed?
## Ingestion
- Source system and ingestion represent the most significant bottleneck of the DE cycle (normally outside tyour control)
- Batch Vs Streaming: Batch is one way door: Once data is broken into batches, latency is constrained, so do decision making speed.
- Pull (ETL) vs Push (CDC: Push logs vs Pull latest changes )
- Considerations:
    - Reuse ingested data vs Use snapshots
    - Reliability when ingesting
    - Compatibility between source and destination
    - Frequency of ingestion - Associated costs
    - Volume of ingestion - Associated costs
    - Allowed formats


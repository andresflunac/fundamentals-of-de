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
    - Communication between producers and consumers
    - Snapshots vs CDC
    - Reading impact


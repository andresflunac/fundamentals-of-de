#  Designing Good Data Architecture
## Introducing Data Architecture
- **About architects:** Architects indentify problems in the current state, define desired future states and realize initiatives through execution of small, concrete steps
- Data engineers must account for trade-offs at every step to design an optimal system while minimizing high-interest technical debt
- Data architecture definition
> Design of systems to support the evolving data needs of an enterprise, achieved by flexible and reversible decisions reached through a careful evaluation of trade-offs
- Data architecture types
    - Operational (WHAT): Functional requirements of what needs to happen related to people, processes, and technology
    - Technical (HOW): How the data is ingested, stored, transformed and served along the DE lifecycle
> Good data architecture serves business requirements with a common, widely *reusable* set of building blocks while maintaining *flexibility* and making appropiate trade-offs
- Reusable, flexible, good trade-offs, easy to maintain vs one-size-fits-all, rigid, overly centralized.

## Principles of Data Engineering Architecture
### 1. Choose common components wisely
When making a decision about the components in your architecture, choose the ones that:
- Facilitate the collaboration between your team
- Aim for reusability
- Aim for security when accessing them
### 2. Plan for Failure
- Plan to comply standards for the following items:
    - Availability: Time percentage that your system keeps operable
    - Reliability: Probability to meet defined standards
    - Recovery time objective: Max downtime accepted
    - Recovery point objective; Max lost information accepted
### 3. Architect for Scalability
- Decision making when scaling vertically (up/down) or horizontally (in/out)
### 4. Architecture is Leadership
> Data architects are responsible for technology decisions and architecture descriptions and disseminating these choices through effective leadership and training.
- In most ways, the most important activity of a data architect is to mentor the development team, to raise their level so they can take on more complex issues
### 5. Always be architecting
- Don't simply maintain the current state, instead, constantly design new and exciting things in response to changes in business and technology
### 6. Build loosely coupled systems
>When the architecture of a system is designed to enable teams to test, deploy, and change systems without dependencies on other teams, teams require little communication to get the work done
### 7. Make reversible decisions
- Given the pace of change, and the decoupling/modularization of technologies across your data architecture, always strive to pick the best-of-breed solutions that work for your today.
### 8. Prioritize security
Data engineers should consider themselves security engineers
### 9. Embrace FinOps
> FinOps: Cultural practice that enables organizations to get maximum business value by helping engineering, finance, technology and business teams to collaborate on **data-driven spending decisions**
- The new challenge for data leaders is to manage budgets, priorities and efficency

## Major Architecture Concepts
- Concepts that are discussed: Domains, services, distributed systems, scalability and designing for failure
- We utilize distributed systems to realize higher overall scaling capacity and increased availability and reliability.
- Architecture tiers: Single (fine for testing purposes) / multitier (data, application logic and presentation layers)
- Monoliths (single codebase running on a single machine that provides both the application and the user interface) vs Microservices (separate decentralized and loosely coupled services)
- Incorporate reversible technology choices that allow for modularity and loose coupling whenever possible
- Single vs multitenant (performance and security considerations differ)
- Event-driven architecture: Events are passed between loosely coupled services
- Brownfield (refactoring / reorganizing existing architecture) vs Greenfield projects (fresh start unconstrained).
> Always prioritize requirements over building something cool. Assess trade-offs, make flexible decisions, strive for positive ROI.

## Examples of Data Architectures
### Data Warehouse
> Subject oriented, integrated, nonvolatile, and time variant collection of data in suport of management decisions.
- Organizational data warehouse architecture:
    - Separates online analytical processing from production databases: Isolate production loads and improves analytics performance
    - Centralizes and organizes data: Serving data in data marts
    - MPP systems bacame popular in 1980: Optimized to scan massive amounts of data in parallel and thus allow high-performance aggregation and statistical calculations
- Cloud data warehouses: Expand the capabilites of MPP systems to cover many big data use cases that required a Hadoop cluster in the very recent past. They can readily process petabytes of data in a single query
- Data marts: Makes data more easily accesible. Provide an additional stage of transformation beyond than provided by the initial ETL, ELT pipelines.
### Data Lake
- Started with HDFS.
- Raise due to cloud-based object storage (cheap and virtually infinite). For processing, spin up clusters and choose the data processing technology: MapReduce, Spark, Ray, Presto, Hive.
> Data grew to unmanageable sizes, with little schema management, data cataloging and discoverability.
- Original data lake concept was essentially write only.
- Simple DML operations (deleting or updating) were painful to implement
> While big data engineers radiated a particular disdain for their counterparts in data warehousing, the latter could point that DWH provided basic data management capabilities, and that SQL was an efficient tool for writing complex, performant queries and transformations
- Big data costs balloned as the complexities of managing Hadoop clusters forced companies to hire large teams of engineers at high salaries
### Lakehouses
- Cloud DWH has evolved to be very simiular to a data lake architecture: Separation of compute from storage, petabyte-scale queries, variety of unstructured and semistructured data, advanced processing technologies (Spark / Beam)
### Modern Data Stack
- Cloud based, plug and play, easy to use, off-the-shelf components to create a modular and cost effective data architecture
### Lambda and Kappa Architectures
- Lambda: You have systems operating independently of each other: batch, streaming and serving. The source system is ideally immutable and append only, sending data to two destinations for processing: stream and batch
- Kappa: Using a stream processing platform as the backbone for all data handling: ingestion, storage and serving.
- While some streaming systems can scale to huge data volumes, they are complex and expensive, batch storage and processing remain much more efficient and cost-effective for enormous historical datasets
### The Dataflow model and Unified batch and streaming
>While the Kappa architecture relies on a unified queuing and storage layer, one still has to confront using different tools for collecting real-time statistics or running batch aggregation jobs (DataFlow model, Apache Beam)
### Architecture for IoT
- Devices, interfacing with devices using IoT gateways (hubs for connecting devices and securely routing devices to the appropriate destinations on the internet)
- Ingestion: Accomulate data and upload it in batches for later analytics processing
- Storage: Depend on the latency requirement: Object storage / messages queues / time-series databases
### Others
Data mesh, data hub, scaled architecture, metadata frist, event-driven architecture, live data stack
## Conclusion
> In the past, architecture was largely orthogonal to engineering. We expect this distinction will dissapear as data engineering, and engineering in general, quickly evolves, becoming more agile, with less separation between engineering and architecture.`
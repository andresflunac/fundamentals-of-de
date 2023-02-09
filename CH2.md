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
- Batch Vs Streaming: Batch is one way door: Once data is broken into batches, latency is constrained, so do decision-making speed.
- Pull (ETL) vs Push (CDC: Push logs vs Pull latest changes )
- Considerations:
    - Reuse ingested data vs Use snapshots
    - Reliability when ingesting: Data quality - disaster recovery
    - Compatibility between source and destination: It's all about connnectors
    - Frequency of ingestion - Associated costs
    - Volume of ingestion - Associated costs
    - Allowed formats
## Transformation
- Different types of transformations: Data wrangling, data modeling, data featurization
- Considerations:
    - What is the associated value when making transformations
    - Which are the business rules?
    - Can the transformations happen in-flight?
## Serving
- Analytics
    - BI (Past and present): BI system maintains a repository of business logic and definitions
    - Operational analytics (present): Promote immediate actions
    - Embedded (customer facing): Different request rates. Access control is critical here.
- ML
- Reverse ETL: Load back into production systems or SaaS applications. The gist is that transformed data will need to be returned to the source systems in some manner, ideally with the correct lineage processes associated.
# Undercurrents
## Security
- Data access: Least privilege principle
- Timing: Allow permissions only for the necessary duration
- Data protection: Encryption, masking. Most of the times, this is a people problem
## Data Management
> Data best practices once reserved for huge companies (data governance, master of data management, data quality) are now filtering down to companies of all sizes and maturity levels (going back to the enterprisey style)
- Data management encompasses the **set of best practices** that data engineers use to accomplish this task (manage the data engineering lifecycle) both tecnically and strategically.
### Data governance
- Data management function to **ensure quality, integrity, security and usability** of the data collected by the organization.
    - Discoverability: Where data comes from, how it's related to other data, what's the meaning of the data
        - Metadata: Data to make the data discoverable and governable.
            - Business metadata: Meaning of the metadata
            - Technical metadata: Schema, lineage, pipeline
            - Operational metadata: Logs, IDs, success flags
            - Reference metadata: Data to classify other data
    - Accountability; Assigning an individual to govern a portion of the data (owner)
    - Quality: What do you get compared with what you expect? 
        - Accuracy, completeness, timeliness
        - Master Data Management: Maintaining a consistent practice of entities and identities becomes more and more challenging
    - Data Modelling and design
        - Modelling: convert data into a usable form. That includes designing the JSON response of an API
        - DEs need to understand modeling best practices as well as develop the flexibility to apply the appropiate level and type of modeling.
    - Data lineage: Highly correlated with metadata
    - Data integration and interoperability
        > While the complexity of interacting with data systems has decreased, the number of systems and the complexity of the pipelines has dramatically increased
    - Data lifecycle management
        - Data archival policies
        - Data retention laws
        - Data destructioin policies
    - Ethics and privacy
## DataOps
- Collection of technical practices, workflows, cultural norms, and architecture patterns:
    - Rapid innovation with experimentation
    - High Quality
    - Better collaboraiton
    - Clear measurement monitoring, transparency
- Agile + DevOps: Improve the release and quality of data products
### Automation
- Change management best practices (Environment, code and data version control)
- CI/CD
- Configuration as code
- Huge oportunities in the deployments
### Observability and monitoring
### Incident response
- Use automation and observability to identify and resolve incidents
## Data Architecture
> A data engineer should first understand the needs of the business and gather requirements for new use cases. Next, a data engineer needs to translate those requirements to design new ways to capture and serve data, balanced of **cost and operational simplicity**. This means knowing the trade-offs with design patterns, technologies, and tools in source systems, ingestion, storage, transformation and serving data.
## Orchestration
- Scheduler vs Orchestrator: An orchestration engine builds in metadata on job dependencies
## Software engineering
- Core data processing code: Code testing methodologies, such as: Unit, regression, integration, end-to-end, and smoke.
- Development of OSS: The new generation of open source tools assists engineers in managing, ehanching, connecting, optimizing, and monitoring data.
- Streaming: SWE closer to streaming challenges
- IaC: Overlaps with DataOps
- Pipelines as code
- General-purpose problem solving: APIs, pull and transform data, handle exceptions, and so forth.
# Conclusion
- DE Lifecycle: Response to a more abstracted world
- A data engineer has several top-level goals across the data lifecycle: **produce optimum ROI and reduce costs (financial and opportunity), reduce risk (security, data quality), and maximize data value and utility**.

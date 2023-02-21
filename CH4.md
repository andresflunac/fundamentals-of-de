# Choosing Technologies Across the Data Engineering Lifecycle
- Core purpose of DE: Design robust and reliable systems to carry data through the full lifecycle and serve it according to the needs of end users.
- Main criteria to choose a tool: Does it add value to a data product and the broader business?
- Architecture is the what, why and when. Tools are used to make the architecture a reality; tools are the how.
- Architecture first, technology second
## Considerations when choosing tools
### Team size and capabilities
- Size: Will determine the bandwidth to manage complex solutions
- Team experience: Complex tools - higher the invested time
- Especially for small teams or teams with weaker technical chops, use as many managed and SaaS tools as possible, and dedicate your limited bandwidth to solving the complex problems that directly add value to the business.
### Speed to Market
- Choose tools that help you to deliver features and data faster while maintaining high quality standards and security.
- Choose tools that help you move quickly, reliably, safely, and securely.
### Interoperability
- Ensure the tools interacts and operates with other technologies
- Always be aware of how simple it will be to connnect your various technologies across the data engineering lifecycle
### Cost Optimization and Business Value
- Total Cost of Ownership (TCO): Direct and indirect costs. The data landscape is changing too quickly to invest in long-term hardware that inevitably goes stale.
- Total Opportunity cost of Ownership: Cost of lost opportunities that we incur in choosing a technology,m an architecture or process.
- How quickly and cheaply can you move to something newer and better?
- FinOps: Applying DevOps like practices of monitoring and dynamically adjusting systems. Make data-driven decisions about expenses.
### Immutable vs Transitory Technologies
- Immutable technologies are object storage, networking, servers and security.
- For languages, SQL
- Authors advice: Evaluaitng tools every two years. Whenever possible, find the immutable technologies along the data engineering lifecycle, and use those as your base. Build transitory tools around the immutables
### Location: On-premise, Cloud, Hybrid Cloud, Multicloud, Edge
- Enterprises that migrate to the cloud often make major deployment errors by not appropiately adapting their practices to the cloud pricing model
- Cloud vendors monetize characteristics such as dirability, reliability, longevity, and predictability: a variety of compute platforms discount their offerings for workloads that are ephemeral or can be arbitrarily interrumpted.
- New generation of applications are rising: Layers on top of cloud providers to abstract the cloud of clouds
> The cloud itself is changing, with a shift from the IaaS model nuilt around Amazon EC2, and more generally toward managed service offerings such as AWS Glue, BigQuery, Snowflake.
- Choose technologies for your current needs and concrete plans for the near future. Have an escape plan.
- The biggest modern success stories of companies building and maintaining hardware involve extraordinary scale
### Build vs Buy
- Invest in building and customizing when doing so will provide a competitive advantage for your business. Otherwise, stand on the shoulders of giants and use what's already available in the market.
- Embrace abstraction
- Tools adoption have evolved from top-down to bottom-up
- Open Source Software
    - Community managed OSS: Mindshare, maturity, troubleshooting, project management, team, developer relations and community management, contributing, roadmap, self-hosting and maintenance, giving back to the community.
    - Commercial OSS: Offer core by free and charge for premium / Offer managed services. Criterias: Value, delivery model, support, releases and bug fixes, sales cycle and pricing, company finances, logos vs revenue, community support
- Propietary walled gardens: Interoperability, mindshare and market share, docummentation and support, pricing, longevity
> Build vs Buy comes back to knowing your competitive advantage and where it makes sense to invest resources toward customization.
### Monolith vs Modular
- Monoliths: Easy to reason about, lower cognitive burden. Excellent option if you want simplicity in reasoning about your architectures and processes.
- Modularity: Components are swappable, and it's possible to create a polyglot (multiprogramming language) application. Modularity allows engineers to choose the best technology for each job or step along the pipeline.

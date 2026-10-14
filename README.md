# Camel Kit Examples

Examples and migration samples for [Camel Kit](https://github.com/luigidemasi/camel-kit).

### Greenfield

| Example | Description |
|---------|-------------|
| [Order processing](order-processing/) | Walk through designing and generating a Kafka-to-PostgreSQL integration. |

### BizTalk → Camel 4

| Example | Description |
|---------|-------------|
| [BizTalk order processing](biztalk-order-processing/) | Migrate sample BizTalk orchestrations, maps, pipelines, schemas, and bindings to Apache Camel. |
| [BizTalk message XPath](biztalk-message-xpath/) | Orchestration with XPath expression-based message manipulation. |
| [BizTalk exception handling](biztalk-exception-handling/) | Scope blocks and exception handlers in orchestrations. |
| [BizTalk SQL stored procedure](biztalk-sql-stored-procedure/) | SQL adapter calling stored procedures with typed schemas and bindings. |
| [BizTalk canonical data model](biztalk-canonical-data-model/) | Multi-map canonical schema pattern with service-to-canonical mappings. |
| [BizTalk XSLT vs mapper](biztalk-xslt-vs-mapper/) | External XSLT, inline XSLT+C#, and functoid-based maps side by side. |
| [BizTalk CBR with LOB](biztalk-cbr-lob-operations/) | Content-based routing with pipeline, maps, schemas, and SQL LOB adapter. |

### MuleSoft → Camel 4

| Example | Description |
|---------|-------------|
| [Mule content-based routing](mule-content-based-routing/) | Choice Router with HTTP listener. |
| [Mule scatter-gather](mule-scatter-gather/) | Scatter-Gather parallel aggregation with custom Java transformers. |
| [Mule JMS rollback & redelivery](mule-jms-rollback-redelivery/) | JMS rollback exception strategy with ActiveMQ redelivery. |
| [Mule REST APIkit](mule-rest-apikit/) | APIkit Router with RAML-defined REST API. |
| [Mule FTP JSON-to-XML](mule-ftp-json-to-xml/) | DataWeave JSON-to-XML transformation with FTP upload. |
| [Mule service orchestration](mule-service-orchestration/) | Multi-flow orchestration with SOAP, JMS, database, and XA transactions. |
| [Mule MySQL query](mule-mysql-query/) | Database connector querying MySQL and returning JSON. |
| [Mule DataWeave orders](mule-dataweave-orders/) | DataWeave transformations with Message Enricher and APIkit. |
| [Weather alert system](weather-alert-system/) | MuleSoft 4 real-time alert system with API polling and email notifications. |

### Camel 2.x → Camel 4

| Example | Description |
|---------|-------------|
| [Camel 2 Spring XML routes](camel2-spring-xml-routes/) | Basic Spring XML Camel context with bean wiring and JMS routing. |
| [Camel 2 routing EIPs](camel2-routing-eips/) | 20 Spring XML routes covering CBR, dynamic router, filter, multicast, recipient list, routing slip, throttler, and wire tap. |
| [Camel 2 transforming](camel2-transforming/) | 14 transformation routes covering JAXB, XSLT, JSON, CSV, XQuery, content enricher, and normalizer. |

The order-processing example is a workflow walkthrough. The migration examples
include source artifacts from BizTalk, MuleSoft, and Camel 2 that can be migrated
to Camel 4 using `/camel-migrate`. Camel routes and infrastructure are generated
by following each example's instructions.

## Getting started

1. [Install Camel Kit and its prerequisites](https://github.com/luigidemasi/camel-kit#installation).
2. Clone this repository:

   ```bash
   git clone https://github.com/luigidemasi/camel-kit-examples.git
   cd camel-kit-examples
   ```

3. Follow an example's README, creating the generated integration in a separate directory.

## Documentation

- [User guide](https://github.com/luigidemasi/camel-kit/blob/main/docs/user-guide.md)
- [Command reference](https://github.com/luigidemasi/camel-kit/blob/main/docs/commands.md)
- [Camel Kit website](https://luigidemasi.github.io/camel-kit-web/)

## Contributing

Add each example in its own directory with a README describing prerequisites,
setup, the workflow to follow, and the expected results. Use placeholders for credentials.
Changes to the CLI or skills belong in the [Camel Kit repository](https://github.com/luigidemasi/camel-kit).

## History and license

These examples were extracted from the `examples/` directory of
[Camel Kit at commit 871abbc5](https://github.com/luigidemasi/camel-kit/tree/871abbc5535650c5c348abef6bf02b12ffd2fa49/examples),
retaining their file history, authors, and commit messages. Extraction changes commit IDs.

Apache License 2.0 — see [LICENSE](LICENSE).

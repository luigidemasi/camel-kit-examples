# BizTalk CBR with LOB Operations

Migrate a BizTalk solution combining content-based routing, a receive pipeline, multiple maps, and SQL LOB adapter operations.

## Source artifacts

| File | Description |
|------|-------------|
| `BizTalk Orchestration1.odx` | Orchestration with content-based routing logic |
| `CBRPromoteOperation.btp` | Receive pipeline promoting operation type for routing |
| `Response.xsd` | Response message schema |
| `Maps/*.btm` | Six maps for canonical-to-LOB and LOB-to-canonical transformations |
| `Schemas/*.xsd` | Six schemas for persons, SQL operations, and adapter bindings |
| `Schemas/WcfSendPort_SqlAdapterBinding_Custom.bindinginfo.xml` | SQL adapter port bindings |
| `CBRwithLOBOperations.btproj` | BizTalk project file |

## Migration

Initialize a new project and copy the BizTalk artifacts:

```bash
camel-kit init biztalk-cbr-migration --ai claude
cp -r *.odx *.btp *.xsd *.btproj Maps Schemas biztalk-cbr-migration/
cd biztalk-cbr-migration
```

Run the migration workflow:

```
/camel-migrate
```

## Expected Camel output

- Camel YAML route with `choice()`/`when()` for content-based routing
- XSLT stylesheets for each map transformation
- `camel-sql` component configuration for database operations
- XML validation replacing the receive pipeline
- `application.properties` with externalized configuration

## Source

[sandroasp/BizTalk-Server-Learning-Path](https://github.com/sandroasp/BizTalk-Server-Learning-Path) (MIT License)

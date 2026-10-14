# BizTalk Message XPath

Migrate a BizTalk orchestration that uses XPath expressions to access and modify message values.

## Source artifacts

| File | Description |
|------|-------------|
| `BizTalk Orchestration1.odx` | Orchestration with expression shapes using XPath to read and write message fields |
| `Schema1.xsd` | Message schema defining the order structure |
| `PropertySchema.xsd` | Promoted property schema for context properties |
| `AccessingAndChangeMessageValuesInOrchestration.btproj` | BizTalk project file |

## Migration

Initialize a new project and copy the BizTalk artifacts:

```bash
camel-kit init biztalk-xpath-migration --ai claude
cp *.odx *.xsd *.btproj biztalk-xpath-migration/
cd biztalk-xpath-migration
```

Run the migration workflow:

```
/camel-migrate
```

## Expected Camel output

- Camel YAML route with XPath expressions replacing orchestration expression shapes
- `application.properties` with externalized configuration

## Source

[sandroasp/BizTalk-Server-Learning-Path](https://github.com/sandroasp/BizTalk-Server-Learning-Path) (MIT License)

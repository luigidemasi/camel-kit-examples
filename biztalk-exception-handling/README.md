# BizTalk Exception Handling

Migrate BizTalk orchestrations with scope blocks and exception handlers.

## Source artifacts

| File | Description |
|------|-------------|
| `Sample1.odx` | Orchestration with basic exception handling using scope and catch blocks |
| `Sample2.odx` | Orchestration with nested scopes and multiple exception types |
| `Schema1.xsd` | Message schema |
| `Web References/` | WSDL and reference files for external web service calls |
| `HandlerExceptionsInsideOrchestration.btproj` | BizTalk project file |

## Migration

Initialize a new project and copy the BizTalk artifacts:

```bash
camel-kit init biztalk-exception-migration --ai claude
cp -r *.odx *.xsd *.btproj "Web References" biztalk-exception-migration/
cd biztalk-exception-migration
```

Run the migration workflow:

```
/camel-migrate
```

## Expected Camel output

- Camel YAML routes with `doTry`/`doCatch` or `onException` clauses
- Error handling configuration in `application.properties`

## Source

[sandroasp/BizTalk-Server-Learning-Path](https://github.com/sandroasp/BizTalk-Server-Learning-Path) (MIT License)

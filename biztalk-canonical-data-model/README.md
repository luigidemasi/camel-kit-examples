# BizTalk Canonical Data Model

Migrate a BizTalk solution using the Canonical Data Model pattern with multiple maps transforming service-specific schemas to a canonical format.

## Source artifacts

| File | Description |
|------|-------------|
| `01-Solution/CanonicalRequest.xsd` | Canonical schema |
| `01-Solution/ServiceSchemas/*.xsd` | Service-specific schemas (AddUser, ChangeUserInfo, etc.) |
| `01-Solution/ServiceSchemasToCanonical/*.btm` | Maps transforming each service schema to canonical format |
| `02-Solution/` | Alternative solution with nested purchase order mapping |
| `CanonicalDataModelPattern.btproj` | BizTalk project file |

## Migration

Initialize a new project and copy the BizTalk artifacts:

```bash
camel-kit init biztalk-canonical-migration --ai claude
cp -r 01-Solution 02-Solution *.btproj biztalk-canonical-migration/
cd biztalk-canonical-migration
```

Run the migration workflow:

```
/camel-migrate
```

## Expected Camel output

- XSLT stylesheets for each service-to-canonical mapping
- Camel YAML routes applying the transformations
- `application.properties` with externalized configuration

## Source

[sandroasp/BizTalk-Server-Learning-Path](https://github.com/sandroasp/BizTalk-Server-Learning-Path) (MIT License)

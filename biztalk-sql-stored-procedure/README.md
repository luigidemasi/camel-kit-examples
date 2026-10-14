# BizTalk SQL Stored Procedure

Migrate a BizTalk orchestration that calls SQL Server stored procedures via the WCF-SQL adapter.

## Source artifacts

| File | Description |
|------|-------------|
| `CallSQLStoredProcedure.odx` | Main orchestration calling a stored procedure |
| `TriggerSchema.xsd` | Trigger message schema |
| `SQL_ProcedureResultSet.dbo.usp_GetCodes.xsd` | SQL result set schema |
| `SQL_TypedProcedure.dbo.xsd` | Typed procedure schema |
| `WcfSendPort_SqlAdapterBinding_Custom.bindinginfo.xml` | WCF-SQL adapter port bindings |
| `01-MostCommonSituation/` | Most common approach with map and typed procedure |
| `02-CrazyApproach/` | Alternative approach variant |
| `03-UnnecessaryApproach/` | Another approach variant for comparison |

## Migration

Initialize a new project and copy the BizTalk artifacts:

```bash
camel-kit init biztalk-sql-migration --ai claude
cp -r *.odx *.xsd *.xml *.btproj 01-* 02-* 03-* biztalk-sql-migration/
cd biztalk-sql-migration
```

Run the migration workflow:

```
/camel-migrate
```

## Expected Camel output

- Camel YAML route using `camel-sql` or `camel-jdbc` component
- XSLT or DataMapper for schema transformations
- `application.properties` with database connection configuration

## Source

[sandroasp/BizTalk-Server-Learning-Path](https://github.com/sandroasp/BizTalk-Server-Learning-Path) (MIT License)

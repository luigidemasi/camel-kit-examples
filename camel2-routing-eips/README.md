# Camel 2 Routing EIPs

Migrate 20 Spring XML Camel 2 routes covering core Enterprise Integration Patterns to Camel 4 YAML DSL.

## Source artifacts

| Path | Description |
|------|-------------|
| `src/main/resources/META-INF/spring/*.xml` | 20 Spring XML route definitions |
| `src/main/java/org/camelcookbook/routing/` | Java DSL RouteBuilder implementations |
| `pom.xml` | Maven project targeting Camel 2.20.0 |

## EIPs covered

Content-based router, dynamic router, message filter, load balancer (failover, sticky), multicast, recipient list, routing slip, throttler, wire tap, and MEP changes.

## Migration

Initialize a new project and copy the Camel 2 source:

```bash
camel-kit init camel2-routing-migration --ai claude
cp -r src pom.xml camel2-routing-migration/
cd camel2-routing-migration
```

Run the migration workflow:

```
/camel-migrate
```

## Expected Camel output

- Camel 4 YAML DSL routes replacing Spring XML definitions
- Updated `pom.xml` with Camel 4 dependencies
- `application.properties` with externalized configuration

## Source

[CamelCookbook/camel-cookbook-examples](https://github.com/CamelCookbook/camel-cookbook-examples) (Apache-2.0 License)

# Camel 2 Transforming

Migrate 14 Spring XML Camel 2 transformation routes to Camel 4 YAML DSL.

## Source artifacts

| Path | Description |
|------|-------------|
| `src/main/resources/META-INF/spring/*.xml` | 14 Spring XML route definitions |
| `src/main/resources/book.xslt` | XSLT stylesheet used by transformation routes |
| `src/main/java/org/camelcookbook/transformation/` | Java DSL RouteBuilder implementations and JAXB model classes |
| `pom.xml` | Maven project targeting Camel 2.20.0 |

## Transformations covered

JAXB marshalling, XSLT, JSON (Jackson and XStream), CSV, XML-JSON, content enricher, normalizer, XQuery, and Simple language.

## Migration

Initialize a new project and copy the Camel 2 source:

```bash
camel-kit init camel2-transform-migration --ai claude
cp -r src pom.xml camel2-transform-migration/
cd camel2-transform-migration
```

Run the migration workflow:

```
/camel-migrate
```

## Expected Camel output

- Camel 4 YAML DSL routes replacing Spring XML definitions
- JAXB annotations updated from `javax.xml.bind` to `jakarta.xml.bind`
- Updated `pom.xml` with Camel 4 dependencies and explicit `camel-jaxb` dependency
- `application.properties` with externalized configuration

## Source

[CamelCookbook/camel-cookbook-examples](https://github.com/CamelCookbook/camel-cookbook-examples) (Apache-2.0 License)

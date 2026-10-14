# BizTalk XSLT vs Mapper

Migrate three variations of BizTalk maps: functoid-based, external XSLT, and inline XSLT with C#.

## Source artifacts

| File | Description |
|------|-------------|
| `MapWithFunctoids.btm` | Map using BizTalk functoids for transformation logic |
| `MapWithExternalXSLT.btm` | Map referencing an external XSLT stylesheet |
| `MapWithInlineXSLTandCSharp.btm` | Map with inline XSLT and embedded C# script |
| `Order.xsd` | Source schema |
| `SAPOrder.xsd` | Target schema |
| `XSLTResources/MapWithExternalXSLT-XSLTFile.xsl` | External XSLT stylesheet |
| `ExternalCustomXSLTvsBizTalkMapper.btproj` | BizTalk project file |

## Migration

Initialize a new project and copy the BizTalk artifacts:

```bash
camel-kit init biztalk-xslt-migration --ai claude
cp -r *.btm *.xsd *.btproj XSLTResources biztalk-xslt-migration/
cd biztalk-xslt-migration
```

Run the migration workflow:

```
/camel-migrate
```

## Expected Camel output

- External XSLT preserved and referenced by Camel XSLT component
- Functoid maps converted to generated XSLT
- Inline XSLT+C# translated to XSLT or Groovy DataMapper
- `application.properties` with externalized configuration

## Source

[sandroasp/BizTalk-Server-Learning-Path](https://github.com/sandroasp/BizTalk-Server-Learning-Path) (MIT License)

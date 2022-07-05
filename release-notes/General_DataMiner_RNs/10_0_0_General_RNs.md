---
uid: 10_0_0_General_RNs
---

# DataMiner 10.0.0 release notes

> [!IMPORTANT]
> We are still working on this release. Some release notes may still be modified or moved to a later release. Check back soon for updates!

## Changes in DataMiner 10.1.0 CU22

### Enhancements

#### Security enhancements

A number of security enhancements have been made.

### Fixes

#### Protocols: Additional connections with a 'Type' defined would incorrectly be ignored [ID_33941]

<!-- Main Release Version 10.0.0 [CU22]/10.1.0 [CU18]/10.2.0 [CU6] - Feature Release Version 10.2.9 -->

Additional connections that had a `<Type>` defined would incorrectly no longer be taken into account.

In the following example, the second connection would incorrectly be ignored.

```xml
<Connections>
    <Connection id="0" name="HTTP Connection">
        <Type>http</Type>
        ...
    </Connection>
    <Connection id="1" name="WebSocket Interface">
        <Type>http</Type>
        ...
```

> [!NOTE]
> Specifying a type with `<Type>` for one connection and specifying a type with e.g. `<Http>` for another connection is not supported.

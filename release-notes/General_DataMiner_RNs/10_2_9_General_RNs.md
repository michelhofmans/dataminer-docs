---
uid: 10_2_9_General_RNs
---

# DataMiner 10.2.9 release notes

> [!IMPORTANT]
> We are still working on this release. Some release notes may still be modified or moved to a later release. Check back soon for updates!

> [!NOTE]
> For release notes related to DataMiner Cube, see [DataMiner Cube 10.2.9 release notes](xref:10_2_9_Cube_RNs).

## Highlights

## Other new features

### Core functionality

#### Specifying a connection setup timeout per connection when creating or editing an element [ID_33053]

<!-- Main Release Version 10.3.0 - Feature Release Version 10.2.9 -->

When creating or editing an element, it is now possible to specify a connection setup timeout (in milliseconds) for each of the following types of connections of that element:

- SSH
- HTTP
- Web Socket
- Serial TCP
- Smart-serial TCP
- Serial SSL/TLS
- GPIB

In the *Element.xml* file of the element in question, this connection timeout setting will be stored in `Port.ConnectTimeoutTime`. See the following example.

```xml
<Port>
    ...
    <ConnectTimeoutTime>30000</ConnectTimeoutTime>
    ...
</Port>
```

#### SLPort: Order of parameters in an HTTP session request will be identical to that in the protocol [ID_33796]

<!-- Main Release Version 10.1.0 [CU18]/10.2.0 [CU6] - Feature Release Version 10.2.9 -->

In an HTTP session request, the order of the parameters will now always be identical to that in the protocol.

#### DVE function protocol version of active functions will now be deleted when the main DVE protocol version is deleted [ID_33834]

<!-- Main Release Version 10.1.0 [CU18]/10.2.0 [CU6] - Feature Release Version 10.2.9 -->

When a version of a DVE protocol with function DVE protocols is deleted from the system while functions are active, from now on, the function DVE protocol versions associated with those active functions will also be removed from the system.

### DMS web apps

#### Web apps now also support parameter comments configured in Param.Message elements [ID_33784]

<!-- Main Release Version 10.3.0 - Feature Release Version 10.2.9 -->

When configuring a parameter in a protocol, you can add a `<Message>` element containing a comment to be displayed in a confirmation box when users change that parameter on the user interface. Up to now, this `<Message>` element was only supported by DataMiner Cube. It is now also supported by web applications like Monitoring and Dashboards.

### DMS tools

## Changes

### Enhancements

#### Cassandra Cluster Migrator: Enhanced resilience of the migration process [ID_33467] [ID_33621] [ID_33727]

<!-- Main Release Version 10.2.0 [CU6] - Feature Release Version 10.2.9 -->

The migration process will now be executed partition by partition. This greatly enhances the overall resilience of that process.

When the source database is a Cassandra database, at the end of a migration process, the Migrator tool will now automatically retry to migrate the partitions that could not be migrated the first time. Moreover, when you manually restart a migration with failed partitions, only those failed partitions will be included in the new migration attempt. The migration will no longer have to be redone from scratch.

Also, additional fail-safes have been built in to cope with situations where the target Cassandra database cannot be reached.

### Fixes

#### SLLogCollector would become unresponsive when the name of the process or the path where the files had to be stored contained spaces [ID_33493]

<!-- Main Release Version 10.1.0 [CU18]/10.2.0 [CU6] - Feature Release Version 10.2.9 -->

While collecting log information, SLLogCollector would become unresponsive when the name of the process or the path where the collected files had to be stored contained spaces.

#### SLProtocol would leak memory leak each time a parameter of a replicated element was updated [ID_33745]

<!-- Main Release Version 10.1.0 [CU18]/10.2.0 [CU6] - Feature Release Version 10.2.9 -->

SLProtocol would leak memory each time a parameter of a replicated element was updated.

#### Web services API would incorrectly no longer clear a number of its caches when the connection was lost [ID_33764]

<!-- Main Release Version 10.3.0 - Feature Release Version 10.2.9 -->

When the connection was lost, the web services API would incorrectly no longer clear a number of its caches.

#### Dashboards app - Service definition component: Function nodes would incorrectly not display the number of Process Automation tokens in queue or in progress [ID_33848]

<!-- Main Release Version 10.3.0 - Feature Release Version 10.2.9 -->
<!-- Not added to 10.3.0 -->

When a Process Automation definition was added to a Service definition component, the function nodes would incorrectly not display the number of tokens currently in queue or in progress.

#### SNMPv3 credentials would incorrectly be checked when replicating an element with SNMPv3 connections [ID_33859]

<!-- Main Release Version 10.1.0 [CU18]/10.2.0 [CU6] - Feature Release Version 10.2.9 -->

When you replicated an element with SNMPv3 connections, the SNMPv3 credentials of that element would incorrectly be checked. As a result, alarms like the following one would appear in the Alarm Console:

```txt
Load Element Failed: Error parsing SNMPv3 password for element: <element name>
```

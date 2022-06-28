---
uid: 10_2_0_General_RNs
---

# DataMiner 10.2.0 release notes

> [!IMPORTANT]
> We are still working on this release. Some release notes may still be modified or moved to a later release. Check back soon for updates!

> [!NOTE]
> For release notes related to DataMiner Cube, see [DataMiner Cube 10.2.9 release notes](xref:10_2_9_Cube_RNs).

## Changes in DataMiner 10.2.0 CU6

### Enhancements

#### Security enhancements 

A number of security enhancements have been made.

#### NATS: Enhancements to the NATS configuration [ID_33558]

<!-- Main Release Version 10.2.0 [CU6] - Feature Release Version 10.2.8 -->

A number of enhancements have been made to the NATS configuration:

- STAN clustering has been removed.
- New NATSForceManualConfig option to disable the automatic reset timer in NATSCustodian.

    Disabling the timer can be done in one of the following ways:

    - Set the SLNet option **NATSForceManualConfig** to true in the SLNetClientTest tool (default = false).
    - Set the **SLNet.NATSForceManualConfig** tag to true in *MaintenanceSettings.xml*.

    > [!NOTE]
    > - Changing this option in the SLNetClientTest tool can be done at run-time. The change will be applied immediately.
    > - Forcing manual configuration will disable the automatic NATS configuration on the DataMiner System. It will then be up to the user to either manually configure a NATS cluster or manually call NatsCustodianResetNatsMessage when changes are made to the DMS.

- On DataMiner startup, NAS and NATS will now automatically be started if they are not running.

Also, the nats-streaming-server binary has been updated to v0.24.6. However, note that it will not be updated automatically via upgrade actions. It will only be installed during fresh NATS installations or when reinstalling NATS via SLEndpointTool_Console. The previous version (v0.22.0) and the new version (v0.24.6) version are compatible and are able to communicate with each other.

#### Dashboards app: Enhanced “loading” indication when state component linked to a GQI query receives an update [ID_33640]

<!-- Main Release Version 10.2.0 [CU6] - Feature Release Version 10.2.8 -->

Up to now, each time a state component linked to a GQI query received an update, a *loading* indication would be displayed over the entire component. From now on, when such a component receives an update, a more subtle loader bar will be displayed instead.

Also, when a query error occur, from now on, the actual error will be displayed instead of "No data".

### Fixes

#### GQI: Datetime values in retrieved booking information would incorrectly not be converted to UTC time [ID_33607]

<!-- Main Release Version 10.2.0 [CU6] - Feature Release Version 10.2.8 -->

When a GQI query retrieved booking information, the datetime values would incorrectly not be converted to UTC time.

---
uid: 10_1_0_Cube_RNs
---

# DataMiner Cube 10.1.0 release notes

> [!IMPORTANT]
> We are still working on this release. Some release notes may still be modified or moved to a later release. Check back soon for updates!

## Changes in DataMiner 10.1.0 CU18

### Enhancements

### Fixes

#### Trending: Creation, update and deletion of a trend pattern would not be communicated to the other DataMiner Agents in the DMS [ID_33624]

<!-- Main Release Version 10.1.0 [CU18]/10.2.0 [CU5] - Feature Release Version 10.2.8 -->

When you created, updated or deleted a tag, up to now, this would incorrectly not be communicated to the other DataMiner Agents in the DMS.

#### SLAnalytics - Pattern matching: No 'suggestion event' type alarm would be triggered in case of DVE elements [ID_32671]

<!-- Main Release Version 10.1.0 [CU18]/10.2.0 [CU6] - Feature Release Version 10.2.5 -->

From DataMiner 10.0.13 onwards, you can activate alarm monitoring of trend patterns, so that a "suggestion event" type alarm is triggered whenever a specific pattern is detected. In case of dynamic virtual elements, in some cases, no "suggestion event" type alarm would be triggered.

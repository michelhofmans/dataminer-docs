---
uid: 10_2_0_Cube_RNs
---

# DataMiner Cube 10.2.0 release notes

> [!IMPORTANT]
> We are still working on this release. Some release notes may still be modified or moved to a later release. Check back soon for updates!

## Changes in DataMiner 10.2.0 CU6

### Enhancements

#### Alarm Console: Time of history sets will now always be converted to the local time zone [ID_33849]

<!-- Main Release Version 10.2.0 [CU6] - Feature Release Version 10.2.9 -->

From now on, the time of history sets will always be converted to the local time zone.

#### Alarm Console - Proactive cap detection: Reduction of false positive matches [ID_33871]

<!-- Main Release Version 10.2.0 [CU6] - Feature Release Version 10.2.9 -->

When trend data is often getting close to the low or high value of a data range, this data range value will no longer be considered as a critical data boundary. This will reduce the number of false positive matches.

### Fixes

#### SLAnalytics - Pattern matching: No 'suggestion event' type alarm would be triggered in case of DVE elements [ID_32671]

<!-- Main Release Version 10.1.0 [CU18]/10.2.0 [CU6] - Feature Release Version 10.2.5 -->

From DataMiner 10.0.13 onwards, you can activate alarm monitoring of trend patterns, so that a "suggestion event" type alarm is triggered whenever a specific pattern is detected. In case of dynamic virtual elements, in some cases, no "suggestion event" type alarm would be triggered.

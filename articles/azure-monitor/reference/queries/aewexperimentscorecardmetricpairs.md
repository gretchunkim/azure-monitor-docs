---
title: Example log table queries for AEWExperimentScorecardMetricPairs
description:  Example queries for AEWExperimentScorecardMetricPairs log table
ms.topic: generated-reference
ms.date: 02/18/2025

# This file is automatically generated. Changes will be overwritten. Do not change this file directly. 

---

# Queries for the AEWExperimentScorecardMetricPairs table

For information on using these queries in the Azure portal, see [Log Analytics tutorial](/azure/azure-monitor/logs/log-analytics-tutorial). For the REST API, see [Query](/rest/api/loganalytics/query).


### Latest scorecard results for a given feature  


Query the latest experiment scorecard result for a given feature.  

```query
// Latest scorecard results for a given feature
// set the feature flag name to query
let QueryFeature = "MyFeatureFlag";
AEWExperimentAssignmentSummary
| where FeatureName == QueryFeature
| summarize arg_max(MaxTimeGenerated, AllocationId)
| join kind=inner AEWExperimentScorecards on AllocationId
| summarize arg_max(TimeGenerated, ScorecardId)
| join kind=inner AEWExperimentScorecardMetricPairs on ScorecardId
| project
    ScorecardId, MetricId, MetricDisplayName, MetricKind, MetricTags,
    TreatmentVariant, TreatmentCount, TreatmentMetricValue,
    ControlVariant, ControlCount, ControlMetricValue,
    TreatmentEffect, RelativeDifference, PValue, Insights
```


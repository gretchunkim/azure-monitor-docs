---
title: Example log table queries for SCGPoolExecutionLog
description:  Example queries for SCGPoolExecutionLog log table
ms.topic: generated-reference
ms.date: 02/18/2025

# This file is automatically generated. Changes will be overwritten. Do not change this file directly. 

---

# Queries for the SCGPoolExecutionLog table

For information on using these queries in the Azure portal, see [Log Analytics tutorial](/azure/azure-monitor/logs/log-analytics-tutorial). For the REST API, see [Query](/rest/api/loganalytics/query).


### Settings Updated Pool Events  


A list of the last 10 settings updates.  

```query
SCGPoolRequestLog
| project TimeGenerated, Location
| sort by TimeGenerated desc
| limit 30
```


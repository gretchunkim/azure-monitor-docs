---
title: Example log table queries for EGNFailedMqttConnections
description:  Example queries for EGNFailedMqttConnections log table
ms.topic: generated-reference
ms.date: 02/18/2025

# This file is automatically generated. Changes will be overwritten. Do not change this file directly. 

---

# Queries for the EGNFailedMqttConnections table

For information on using these queries in the Azure portal, see [Log Analytics tutorial](/azure/azure-monitor/logs/log-analytics-tutorial). For the REST API, see [Query](/rest/api/loganalytics/query).


### Authentication error query  


Authentication errors report by session name.  

```query
EGNFailedMqttConnections
| where ResultSignature == "AuthenticationError"
| summarize count() by SessionName
```


---
title: Example log table queries for ADTQueryOperation
description:  Example queries for ADTQueryOperation log table
ms.topic: generated-reference
ms.date: 02/18/2025

# This file is automatically generated. Changes will be overwritten. Do not change this file directly. 

---

# Queries for the ADTQueryOperation table

For information on using these queries in the Azure portal, see [Log Analytics tutorial](/azure/azure-monitor/logs/log-analytics-tutorial). For the REST API, see [Query](/rest/api/loganalytics/query).


### Query Error Summary  


List of all Query call errors.  

```query
ADTQueryOperation
| where ResultType != 'Success'
```


---
UID: NF:ntddndis.NDIS_ROUTING_DOMAIN_ENTRY_GET_FIRST_ISOLATION_ENTRY
title: NDIS_ROUTING_DOMAIN_ENTRY_GET_FIRST_ISOLATION_ENTRY macro (ntddndis.h)
description: The NDIS_ROUTING_DOMAIN_ENTRY_GET_FIRST_ISOLATION_ENTRY macro is used to access the first NDIS_ROUTING_DOMAIN_ISOLATION_ENTRY that is specified by an NDIS_ROUTING_DOMAIN_ENTRY structure.
tech.root: netvista
ms.date: 04/17/2018
keywords: ["NDIS_ROUTING_DOMAIN_ENTRY_GET_FIRST_ISOLATION_ENTRY macro"]
ms.keywords: NDIS_ROUTING_DOMAIN_ENTRY_GET_FIRST_ISOLATION_ENTRY
req.header: ntddndis.h
req.include-header: ndis.h
req.target-type: Desktop
req.target-min-winverclnt: Supported in NDIS 6.40 and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: 
req.dll: 
req.irql: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
targetos: Windows
returns-override: true
f1_keywords:
 - NDIS_ROUTING_DOMAIN_ENTRY_GET_FIRST_ISOLATION_ENTRY
 - ntddndis/NDIS_ROUTING_DOMAIN_ENTRY_GET_FIRST_ISOLATION_ENTRY
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ntddndis.h
api_name:
 - NDIS_ROUTING_DOMAIN_ENTRY_GET_FIRST_ISOLATION_ENTRY
---

# NDIS_ROUTING_DOMAIN_ENTRY_GET_FIRST_ISOLATION_ENTRY macro


## -description

The **NDIS_ROUTING_DOMAIN_ENTRY_GET_FIRST_ISOLATION_ENTRY** macro is used to access the first [**NDIS_ROUTING_DOMAIN_ISOLATION_ENTRY**](ns-ntddndis-_ndis_routing_domain_isolation_entry.md) that is specified by an [**NDIS_ROUTING_DOMAIN_ENTRY**](ns-ntddndis-_ndis_routing_domain_entry.md) structure.

## -parameters

### -param _RoutingDomainEntry_

A pointer to an **NDIS_ROUTING_DOMAIN_ENTRY** structure.

## -returns

The **NDIS_ROUTING_DOMAIN_ENTRY_GET_FIRST_ISOLATION_ENTRY** macro returns a pointer to the first [**NDIS_ROUTING_DOMAIN_ISOLATION_ENTRY**](ns-ntddndis-_ndis_routing_domain_isolation_entry.md) element in the array.

## -remarks

## -see-also

[**NDIS_ROUTING_DOMAIN_ENTRY**](ns-ntddndis-_ndis_routing_domain_entry.md)

[**NDIS_ROUTING_DOMAIN_ISOLATION_ENTRY**](ns-ntddndis-_ndis_routing_domain_isolation_entry.md)


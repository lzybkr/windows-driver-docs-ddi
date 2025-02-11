---
UID: NE:netpoweroffload._NET_POWER_OFFLOAD_TYPE
title: NET_POWER_OFFLOAD_TYPE (netpoweroffload.h)
description: The NET_POWER_OFFLOAD_TYPE enumeration specifies the type for a low power offload protocol offload to a net adapter.
tech.root: netvista
ms.date: 04/01/2022
keywords: ["NET_POWER_OFFLOAD_TYPE enumeration"]
ms.keywords: NET_POWER_OFFLOAD_TYPE, NET_POWER_OFFLOAD_TYPE,
req.header: netpoweroffload.h
req.include-header: netadaptercx.h
req.target-type: 
req.target-min-winverclnt: Windows 10, version 2004
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 2.33 
req.ddi-compliance: 
req.max-support: 
req.typenames: NET_POWER_OFFLOAD_TYPE
targetos: Windows
ms.custom: Vb
f1_keywords:
 - _NET_POWER_OFFLOAD_TYPE
 - netpoweroffload/_NET_POWER_OFFLOAD_TYPE
 - NET_POWER_OFFLOAD_TYPE
 - netpoweroffload/NET_POWER_OFFLOAD_TYPE
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - netpoweroffload.h
api_name:
 - _NET_POWER_OFFLOAD_TYPE
 - NET_POWER_OFFLOAD_TYPE
---

# NET_POWER_OFFLOAD_TYPE enumeration


## -description

The **NET_POWER_OFFLOAD_TYPE** enumeration specifies the type for a low power offload protocol offload to a net adapter.

## -enum-fields

### -field NetPowerOffloadTypeArp:1 

The power offload is the IPv4 ARP protocol.

### -field NetPowerOffloadTypeNS:2 

The power offload is the IPv6 Neighbor Solicitation (NS) protocol.

## -remarks

Call [**NetPowerOffloadGetType**](../netpoweroffload/nf-netpoweroffload-netpoweroffloadgettype.md) to get the type for a low power protocol offload.

## -see-also

[Configuring power management](/windows-hardware/drivers/netcx/configuring-power-management)


---
UID: NF:netadapter.NetAdapterWakeSetPacketFilterCapabilities
title: NetAdapterWakeSetPacketFilterCapabilities function (netadapter.h)
description: The NetAdapterWakeSetPacketFilterCapabilities function sets a net adapter's packet filter wake on LAN (WoL) capabilities.
tech.root: netvista
ms.date: 10/25/2019
keywords: ["NetAdapterWakeSetPacketFilterCapabilities function"]
ms.keywords: NetAdapterWakeSetPacketFilterCapabilities
req.header: netadapter.h
req.include-header: netadaptercx.h 
req.target-type: Universal
req.target-min-winverclnt: Windows 10, version 2004
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 2.33 
req.lib: netadaptercxstub.lib
req.dll: 
req.irql: PASSIVE_LEVEL
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
targetos: Windows
ms.custom: Vb
f1_keywords:
 - NetAdapterWakeSetPacketFilterCapabilities
 - netadapter/NetAdapterWakeSetPacketFilterCapabilities
topic_type:
 - apiref
api_type:
 - LibDef
api_location:
 - netadaptercxstub.lib
api_name:
 - NetAdapterWakeSetPacketFilterCapabilities
---

# NetAdapterWakeSetPacketFilterCapabilities function


## -description

The **NetAdapterWakeSetPacketFilterCapabilities** function sets a net adapter's packet filter wake on LAN (WoL) capabilities.

## -parameters

### -param Adapter [_In_]

A handle to a NETADAPTER object that the client driver obtained from a previous call to [**NetAdapterCreate**](../netadapter/nf-netadapter-netadaptercreate.md).

### -param Capabilities [_In_]

A pointer to a client driver-allocated and initialized [**NET_ADAPTER_WAKE_PACKET_FILTER_CAPABILITIES**](../netadapter/ns-netadapter-_net_adapter_wake_packet_filter_capabilities.md) structure.


## -remarks

Client drivers must call [**NET_ADAPTER_WAKE_PACKET_FILTER_CAPABILITIES_INIT**](../netadapter/nf-netadapter-net_adapter_wake_packet_filter_capabilities_init.md) to initialize the **NET_ADAPTER_WAKE_PACKET_FILTER_CAPABILITIES** structure, then set the structure's members appropriately before calling this function. Client drivers typically call this function from within their [*EvtDevicePrepareHardware*](../wdfdevice/nc-wdfdevice-evt_wdf_device_prepare_hardware.md) callback, but **must** call this function before calling [**NetAdapterStart**](nf-netadapter-netadapterstart.md).

## -see-also

[Configuring power management](/windows-hardware/drivers/netcx/configuring-power-management)

[**NET_ADAPTER_WAKE_PACKET_FILTER_CAPABILITIES**](../netadapter/ns-netadapter-_net_adapter_wake_packet_filter_capabilities.md)

[**NET_ADAPTER_WAKE_PACKET_FILTER_CAPABILITIES_INIT**](../netadapter/nf-netadapter-net_adapter_wake_packet_filter_capabilities_init.md)

[**NetAdapterCreate**](../netadapter/nf-netadapter-netadaptercreate.md)

[*EvtDevicePrepareHardware*](../wdfdevice/nc-wdfdevice-evt_wdf_device_prepare_hardware.md)

[**NetAdapterStart**](nf-netadapter-netadapterstart.md)

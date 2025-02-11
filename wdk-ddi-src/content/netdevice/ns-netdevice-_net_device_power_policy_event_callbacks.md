---
UID: NS:netdevice._NET_DEVICE_POWER_POLICY_EVENT_CALLBACKS
title: NET_DEVICE_POWER_POLICY_EVENT_CALLBACKS (netdevice.h)
description: The NET_DEVICE_POWER_POLICY_EVENT_CALLBACKS structure contains function pointers for a client driver's power policy callback functions.
tech.root: netvista
ms.date: 10/11/2019
keywords: ["NET_DEVICE_POWER_POLICY_EVENT_CALLBACKS structure"]
ms.keywords: NET_DEVICE_POWER_POLICY_EVENT_CALLBACKS, NET_DEVICE_POWER_POLICY_EVENT_CALLBACKS,
req.header: netdevice.h
req.include-header: netadaptercx.h
req.target-type: 
req.target-min-winverclnt: Windows 10, version 2004
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 2.33 
req.lib: 
req.dll: 
req.ddi-compliance: 
req.unicode-ansi: 
req.max-support: 
req.typenames: NET_DEVICE_POWER_POLICY_EVENT_CALLBACKS
targetos: Windows
ms.custom: Vb
f1_keywords:
 - _NET_DEVICE_POWER_POLICY_EVENT_CALLBACKS
 - netdevice/_NET_DEVICE_POWER_POLICY_EVENT_CALLBACKS
 - NET_DEVICE_POWER_POLICY_EVENT_CALLBACKS
 - netdevice/NET_DEVICE_POWER_POLICY_EVENT_CALLBACKS
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - netdevice.h
api_name:
 - _NET_DEVICE_POWER_POLICY_EVENT_CALLBACKS
 - NET_DEVICE_POWER_POLICY_EVENT_CALLBACKS
---

# NET_DEVICE_POWER_POLICY_EVENT_CALLBACKS structure


## -description

The **NET_DEVICE_POWER_POLICY_EVENT_CALLBACKS** structure contains function pointers for a client driver's power policy callback functions.

## -struct-fields

### -field Size

The size of this structure, in bytes.

### -field EvtDevicePreviewBitmapPattern

A pointer to the client driver's implementation of the [*EvtNetDevicePreviewWakeSource*](../netdevice/nc-netdevice-evt_net_device_preview_wake_source.md) callback function for previewing a bitmap wake pattern.

### -field EvtDevicePreviewArpOffload

A pointer to an implementation of the [*EvtNetDevicePreviewPowerOffload*](../netdevice/nc-netdevice-evt_net_device_preview_power_offload.md) callback function for previewing an IPv4 ARP low power protocol offload.

### -field EvtDevicePreviewNSOffload

 
A pointer to an implementation of the [*EvtNetDevicePreviewPowerOffload*](../netdevice/nc-netdevice-evt_net_device_preview_power_offload.md) callback function for previewing an IPv6 Neighbor Solicitation (NS) low power protocol offload.

## -remarks

Call [**NET_DEVICE_POWER_POLICY_EVENT_CALLBACKS_INIT**](../netdevice/nf-netdevice-net_device_power_policy_event_callbacks_init.md) to initialize this structure, then provide pointers to the callbacks your client driver implements. If your client driver does not implement one of the callbacks, set that member to **NULL**.

## -see-also

[Configuring Power Management](/windows-hardware/drivers/netcx/configuring-power-management)

[*EvtNetDevicePreviewWakeSource*](../netdevice/nc-netdevice-evt_net_device_preview_wake_source.md)

[*EvtNetDevicePreviewPowerOffload*](../netdevice/nc-netdevice-evt_net_device_preview_power_offload.md)

[**NET_DEVICE_POWER_POLICY_EVENT_CALLBACKS_INIT**](../netdevice/nf-netdevice-net_device_power_policy_event_callbacks_init.md)


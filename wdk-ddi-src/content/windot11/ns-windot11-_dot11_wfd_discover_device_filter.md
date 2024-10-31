---
UID: NS:windot11._DOT11_WFD_DISCOVER_DEVICE_FILTER
title: _DOT11_WFD_DISCOVER_DEVICE_FILTER (windot11.h)
description: The DOT11_WFD_DISCOVER _DEVICE_FILTER structure describes a P2P device and Group Owner filter when responding to OID_DOT11_WFD_DISCOVERY_REQUEST requests.
old-location: netvista\dot11_wfd_discover_device_filter.htm
tech.root: netvista
ms.date: 02/16/2018
keywords: ["DOT11_WFD_DISCOVER_DEVICE_FILTER structure"]
ms.keywords: "*PDOT11_WFD_DISCOVER_DEVICE_FILTER, DOT11_WFD_DISCOVER_DEVICE_FILTER, DOT11_WFD_DISCOVER_DEVICE_FILTER structure [Network Drivers Starting with Windows Vista], PDOT11_WFD_DISCOVER_DEVICE_FILTER, PDOT11_WFD_DISCOVER_DEVICE_FILTER structure pointer [Network Drivers Starting with Windows Vista], _DOT11_WFD_DISCOVER_DEVICE_FILTER, netvista.dot11_wfd_discover_device_filter, windot11/DOT11_WFD_DISCOVER_DEVICE_FILTER, windot11/PDOT11_WFD_DISCOVER_DEVICE_FILTER"
req.header: windot11.h
req.include-header: Windot11.h
req.target-type: Windows
req.target-min-winverclnt: Versions:\_Supported in Windows 8
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
targetos: Windows
req.typenames: DOT11_WFD_DISCOVER_DEVICE_FILTER, *PDOT11_WFD_DISCOVER_DEVICE_FILTER
f1_keywords:
 - _DOT11_WFD_DISCOVER_DEVICE_FILTER
 - windot11/_DOT11_WFD_DISCOVER_DEVICE_FILTER
 - PDOT11_WFD_DISCOVER_DEVICE_FILTER
 - windot11/PDOT11_WFD_DISCOVER_DEVICE_FILTER
 - DOT11_WFD_DISCOVER_DEVICE_FILTER
 - windot11/DOT11_WFD_DISCOVER_DEVICE_FILTER
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Windot11.h
api_name:
 - _DOT11_WFD_DISCOVER_DEVICE_FILTER
 - PDOT11_WFD_DISCOVER_DEVICE_FILTER
 - DOT11_WFD_DISCOVER_DEVICE_FILTER
---

# _DOT11_WFD_DISCOVER_DEVICE_FILTER structure


## -description

> [!Important]
> [WiFiCx](/windows-hardware/drivers/netcx/wifi-wdf-class-extension-wificx) is the new Wi-Fi driver model released in Windows 11. We recommend that you use WiFiCx to take advantage of the latest features. The WDI driver model is now in maintenance mode and will only receive high priority fixes.

The <b>DOT11_WFD_DISCOVER _DEVICE_FILTER</b> structure describes a P2P device and Group Owner filter when responding to OID_DOT11_WFD_DISCOVERY_REQUEST requests.

## -struct-fields

### -field DeviceID

The device address of a P2P Device or Group Owner to be discovered by the local P2P device.

### -field ucBitmask

Filters which instances of the P2P device to discover. Possible values include:



<table>
<tr>
<th>Term</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<a id="DISCOVERY_FILTER_BITMASK_DEVICE"></a><a id="discovery_filter_bitmask_device"></a>DISCOVERY_FILTER_BITMASK_DEVICE

</td>
<td width="60%">
The local P2P device discovers the P2P device with the desired <b>DeviceID</b>.

</td>
</tr>
<tr>
<td width="40%">
<a id="_DISCOVERY_FILTER_BITMASK_GO"></a><a id="_discovery_filter_bitmask_go"></a> DISCOVERY_FILTER_BITMASK_GO

</td>
<td width="60%">
The local P2P device discovers a group with P2P group ID matching the specified <b>DeviceID</b> and <b>GroupSSID</b>.

</td>
</tr>
<tr>
<td width="40%">
<a id="DISCOVERY_FILTER_BITMASK_ANY"></a><a id="discovery_filter_bitmask_any"></a>DISCOVERY_FILTER_BITMASK_ANY

</td>
<td width="60%">
 The local P2P device needs only to discover the P2P device or any group owner hosted by the P2P device.

</td>
</tr>
</table>

### -field GroupSSID

If GroupSSID is not a zero-length SSID, this member specifies the SSID of a P2P group that the local P2P device discovers. If this is the P2P wildcard SSID ("DIRECT-"), the local P2P device discovers all groups with P2P Group ID matching the desired device ID.

## -syntax

```cpp
typedef struct _DOT11_WFD_DISCOVER_DEVICE_FILTER {
  DOT11_MAC_ADDRESS DeviceID;
  UCHAR             ucBitmask;
  DOT11_SSID        GroupSSID;
} DOT11_WFD_DISCOVER_DEVICE_FILTER, *PDOT11_WFD_DISCOVER_DEVICE_FILTER;
```

## -remarks

The local P2P device should not extend the discovery operation to find additional instances.

Note that if the value of <b>ucBitmask</b> is FILTER_BITMASK_DEVICE | FILTER_BITMASK_GO, the local P2P device should discover only one instance of the P2P device - either the P2P device or a GO with the desired P2P <b>DeviceID</b> and <b>GroupSSID</b>.


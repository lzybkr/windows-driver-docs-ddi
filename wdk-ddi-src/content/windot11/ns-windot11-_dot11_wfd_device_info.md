---
UID: NS:windot11._DOT11_WFD_DEVICE_INFO
title: _DOT11_WFD_DEVICE_INFO (windot11.h)
description: the DOT11_WFD_DEVICE_INFO structure is included with a OID_DOT11_WFD_DEVICE_INFO request. The structure contains Wi-Fi Direct (WFD) device information related to Peer-to-Peer (P2P) attributes.
old-location: netvista\_dot11_wfd_device_info.htm
tech.root: netvista
ms.date: 02/16/2018
keywords: ["DOT11_WFD_DEVICE_INFO structure"]
ms.keywords: "*PDOT11_WFD_DEVICE_INFO, DOT11_WFD_DEVICE_INFO, DOT11_WFD_DEVICE_INFO structure [Network Drivers Starting with Windows Vista], PDOT11_WFD_DEVICE_INFO, PDOT11_WFD_DEVICE_INFO structure pointer [Network Drivers Starting with Windows Vista], _DOT11_WFD_DEVICE_INFO, netvista._dot11_wfd_device_info, windot11/ DOT11_WFD_DEVICE_INFO, windot11/PDOT11_WFD_DEVICE_INFO"
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
req.typenames: DOT11_WFD_DEVICE_INFO, *PDOT11_WFD_DEVICE_INFO
f1_keywords:
 - _DOT11_WFD_DEVICE_INFO
 - windot11/_DOT11_WFD_DEVICE_INFO
 - PDOT11_WFD_DEVICE_INFO
 - windot11/PDOT11_WFD_DEVICE_INFO
 - DOT11_WFD_DEVICE_INFO
 - windot11/DOT11_WFD_DEVICE_INFO
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Windot11.h
api_name:
 - _DOT11_WFD_DEVICE_INFO
 - PDOT11_WFD_DEVICE_INFO
 - DOT11_WFD_DEVICE_INFO
---

# _DOT11_WFD_DEVICE_INFO structure


## -description

> [!Important]
> [WiFiCx](/windows-hardware/drivers/netcx/wifi-wdf-class-extension-wificx) is the new Wi-Fi driver model released in Windows 11. We recommend that you use WiFiCx to take advantage of the latest features. The WDI driver model is now in maintenance mode and will only receive high priority fixes.

the <b>DOT11_WFD_DEVICE_INFO</b> structure is included with a <a href="/windows-hardware/drivers/network/oid-dot11-wfd-device-info">OID_DOT11_WFD_DEVICE_INFO</a> request. The structure contains  Wi-Fi Direct (WFD) device information related to Peer-to-Peer (P2P) attributes.

## -struct-fields

### -field Header

Specifies the type, revision and size of the <b>DOT11_WFD_DEVICE_INFO</b> structure. The required settings for the members of <b>Header</b> are the following:

<table>
<tr>
<th>Member</th>
<th>Setting</th>
</tr>
<tr>
<td><b>Type</b></td>
<td>NDIS_OBJECT_TYPE_DEFAULT</td>
</tr>
<tr>
<td><b>Revision</b></td>
<td>DOT11_WFD_DEVICE_INFO_REVISION_1</td>
</tr>
<tr>
<td><b>Size</b></td>
<td>DOT11_SIZEOF_WFD_DEVICE_INFO_REVISION_1</td>
</tr>
</table>

### -field DeviceAddress

The device address to assign to a WFD port. This address is used when constructing P2P Information Elements (IEs).

### -field ConfigMethods

The configuration methods supported by the WFD device.

### -field PrimaryDeviceType

The primary device type for the WFD device.

### -field DeviceName

A friendly name assigned to the WFD device.

## -syntax

```cpp
typedef struct _DOT11_WFD_DEVICE_INFO {
  NDIS_OBJECT_HEADER    Header;
  DOT11_MAC_ADDRESS     DeviceAddress;
  USHORT                ConfigMethods;
  DOT11_WPS_DEVICE_TYPE PrimaryDeviceType;
  DOT11_WPS_DEVICE_NAME DeviceName;
} DOT11_WFD_DEVICE_INFO, *PDOT11_WFD_DEVICE_INFO;
```


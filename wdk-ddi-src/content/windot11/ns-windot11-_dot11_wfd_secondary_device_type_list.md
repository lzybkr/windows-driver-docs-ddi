---
UID: NS:windot11._DOT11_WFD_SECONDARY_DEVICE_TYPE_LIST
title: _DOT11_WFD_SECONDARY_DEVICE_TYPE_LIST (windot11.h)
description: the DOT11_WFD_SECONDARY_DEVICE_TYPE_LIST structure is included with a OID_DOT11_WFD_SECONDARY_DEVICE_TYPE_LIST request. The structure contains the list of secondary device types advertised by a Wi-Fi Direct device.
old-location: netvista\_dot11_wfd_secondary_device_type_list.htm
tech.root: netvista
ms.date: 02/16/2018
keywords: ["DOT11_WFD_SECONDARY_DEVICE_TYPE_LIST structure"]
ms.keywords: "*PDOT11_WFD_SECONDARY_DEVICE_TYPE_LIST, DOT11_WFD_SECONDARY_DEVICE_TYPE_LIST, DOT11_WFD_SECONDARY_DEVICE_TYPE_LIST structure [Network Drivers Starting with Windows Vista], PDOT11_WFD_SECONDARY_DEVICE_TYPE_LIST, PDOT11_WFD_SECONDARY_DEVICE_TYPE_LIST structure pointer [Network Drivers Starting with Windows Vista], _DOT11_WFD_SECONDARY_DEVICE_TYPE_LIST, netvista._dot11_wfd_secondary_device_type_list, windot11/ DOT11_WFD_SECONDARY_DEVICE_TYPE_LIST, windot11/PDOT11_WFD_SECONDARY_DEVICE_TYPE_LIST"
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
req.typenames: DOT11_WFD_SECONDARY_DEVICE_TYPE_LIST, *PDOT11_WFD_SECONDARY_DEVICE_TYPE_LIST
f1_keywords:
 - _DOT11_WFD_SECONDARY_DEVICE_TYPE_LIST
 - windot11/_DOT11_WFD_SECONDARY_DEVICE_TYPE_LIST
 - PDOT11_WFD_SECONDARY_DEVICE_TYPE_LIST
 - windot11/PDOT11_WFD_SECONDARY_DEVICE_TYPE_LIST
 - DOT11_WFD_SECONDARY_DEVICE_TYPE_LIST
 - windot11/DOT11_WFD_SECONDARY_DEVICE_TYPE_LIST
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Windot11.h
api_name:
 - _DOT11_WFD_SECONDARY_DEVICE_TYPE_LIST
 - PDOT11_WFD_SECONDARY_DEVICE_TYPE_LIST
 - DOT11_WFD_SECONDARY_DEVICE_TYPE_LIST
---

# _DOT11_WFD_SECONDARY_DEVICE_TYPE_LIST structure


## -description

> [!Important]
> [WiFiCx](/windows-hardware/drivers/netcx/wifi-wdf-class-extension-wificx) is the new Wi-Fi driver model released in Windows 11. We recommend that you use WiFiCx to take advantage of the latest features. The WDI driver model is now in maintenance mode and will only receive high priority fixes.

the <b>DOT11_WFD_SECONDARY_DEVICE_TYPE_LIST</b> structure is included with a <a href="/windows-hardware/drivers/network/oid-dot11-wfd-secondary-device-type-list">OID_DOT11_WFD_SECONDARY_DEVICE_TYPE_LIST</a> request. The structure contains the list of secondary device types advertised by a Wi-Fi Direct device.

## -struct-fields

### -field Header

Specifies the type, revision and size of the <b>DOT11_WFD_SECONDARY_DEVICE_TYPE_LIST</b> structure. The required settings for the members of <b>Header</b> are the following:

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
<td>DOT11_WFD_SECONDARY_DEVICE_TYPE_LIST_REVISION_1</td>
</tr>
<tr>
<td><b>Size</b></td>
<td>DOT11_SIZEOF_WFD_SECONDARY_DEVICE_TYPE_LIST_REVISION_1</td>
</tr>
</table>

### -field uNumOfEntries

The number of entries present in <b>SecondaryDeviceTypes</b>.

### -field uTotalNumOfEntries

The maximum number of entries the <b>SecondaryDeviceTypes</b> array can contain.

### -field SecondaryDeviceTypes

An array of secondary device types.

## -syntax

```cpp
typedef struct _DOT11_WFD_SECONDARY_DEVICE_TYPE_LIST {
  NDIS_OBJECT_HEADER    Header;
  ULONG                 uNumOfEntries;
  ULONG                 uTotalNumOfEntries;
  DOT11_WFD_DEVICE_TYPE SecondaryDeviceTypes[1];
}  DOT11_WFD_SECONDARY_DEVICE_TYPE_LIST, *PDOT11_WFD_SECONDARY_DEVICE_TYPE_LIST;
```


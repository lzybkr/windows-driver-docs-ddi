---
UID: NS:windot11._DOT11_MAC_PARAMETERS
title: _DOT11_MAC_PARAMETERS (windot11.h)
description: The DOT11_MAC_PARAMETERS is the optional input for an OID_DOT11_CREATE_MAC request. The device role is defined in an operation mode bitmask included in this structure.
old-location: netvista\dot11_mac_parameters.htm
tech.root: netvista
ms.date: 02/16/2018
keywords: ["DOT11_MAC_PARAMETERS structure"]
ms.keywords: "*PDOT11_MAC_PARAMETERS, DOT11_MAC_PARAMETERS, DOT11_MAC_PARAMETERS structure [Network Drivers Starting with Windows Vista], PDOT11_MAC_PARAMETERS, PDOT11_MAC_PARAMETERS structure pointer [Network Drivers Starting with Windows Vista], Revision, Size, Type, _DOT11_MAC_PARAMETERS, netvista.dot11_mac_parameters, windot11/DOT11_MAC_PARAMETERS, windot11/PDOT11_MAC_PARAMETERS"
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
req.typenames: DOT11_MAC_PARAMETERS, *PDOT11_MAC_PARAMETERS
f1_keywords:
 - _DOT11_MAC_PARAMETERS
 - windot11/_DOT11_MAC_PARAMETERS
 - PDOT11_MAC_PARAMETERS
 - windot11/PDOT11_MAC_PARAMETERS
 - DOT11_MAC_PARAMETERS
 - windot11/DOT11_MAC_PARAMETERS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Windot11.h
api_name:
 - _DOT11_MAC_PARAMETERS
 - PDOT11_MAC_PARAMETERS
 - DOT11_MAC_PARAMETERS
---

# _DOT11_MAC_PARAMETERS structure


## -description

> [!Important]
> [WiFiCx](/windows-hardware/drivers/netcx/wifi-wdf-class-extension-wificx) is the new Wi-Fi driver model released in Windows 11. We recommend that you use WiFiCx to take advantage of the latest features. The WDI driver model is now in maintenance mode and will only receive high priority fixes.

The <b>DOT11_MAC_PARAMETERS</b> is the optional input for an <a href="/windows-hardware/drivers/network/oid-dot11-create-mac">OID_DOT11_CREATE_MAC</a> request. The device role is defined in an operation mode bitmask included in this structure.

## -struct-fields

### -field Header

The object header identifying the type and revision of this structure. The required member settings of <a href="..\objectheader\ns-objectheader-ndis_object_header.md">NDIS_OBJECT_HEADER</a> are the following:



#### Type

Must be set to <b>NDIS_OBJECT_TYPE_DEFAULT</b>



#### Revision

Must be set to <b>DOT11_MAC_PARAMETERS_REVISION_1</b>



#### Size

Must be set to <b>DOT11_SIZEOF_MAC_PARAMETERS_REVISION_1</b>

### -field uOpmodeMask

A bitwise OR value of the operation modes Windows may set for the created port. This bitmask is defined through the following:





#### DOT11_OPERATION_MODE_WFD_DEVICE

Specifies that the miniport driver supports the Wi-Fi Direct Device operation mode.



#### DOT11_OPERATION_MODE_WFD_GROUP_OWNER

Specifies that the miniport driver supports the Wi-Fi Direct Group Owner operation mode.



#### DOT11_OPERATION_MODE_WFD_CLIENT

Specifies that the miniport driver supports the Wi-Fi Direct Client operation mode.

## -syntax

```cpp
typedef struct _DOT11_MAC_PARAMETERS {
  NDIS_OBJECT_HEADER Header;
  ULONG              uOpmodeMask;
} DOT11_MAC_PARAMETERS, *PDOT11_MAC_PARAMETERS;
```

## -see-also

<a href="/windows-hardware/drivers/network/oid-dot11-create-mac">OID_DOT11_CREATE_MAC</a>



<a href="..\objectheader\ns-objectheader-ndis_object_header.md">NDIS_OBJECT_HEADER</a>


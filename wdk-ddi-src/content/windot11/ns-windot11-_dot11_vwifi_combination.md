---
UID: NS:windot11._DOT11_VWIFI_COMBINATION
title: _DOT11_VWIFI_COMBINATION (windot11.h)
description: The DOT11_VWIFI_COMBINATION structure is part of the Native 802.11 Wireless LAN interface, which is deprecated for Windows 10 and later.
old-location: netvista\dot11_vwifi_combination.htm
tech.root: netvista
ms.date: 02/16/2018
keywords: ["DOT11_VWIFI_COMBINATION structure"]
ms.keywords: "*PDOT11_VWIFI_COMBINATION, DOT11_VWIFI_COMBINATION, DOT11_VWIFI_COMBINATION structure [Network Drivers Starting with Windows Vista], Native_802.11_data_types_6b9469d7-deb2-4681-8f03-5ff6137946b4.xml, PDOT11_VWIFI_COMBINATION, PDOT11_VWIFI_COMBINATION structure pointer [Network Drivers Starting with Windows Vista], _DOT11_VWIFI_COMBINATION, netvista.dot11_vwifi_combination, windot11/DOT11_VWIFI_COMBINATION, windot11/PDOT11_VWIFI_COMBINATION"
req.header: windot11.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows 7 and later versions of the Windows operating   systems.
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
req.typenames: DOT11_VWIFI_COMBINATION, *PDOT11_VWIFI_COMBINATION
f1_keywords:
 - _DOT11_VWIFI_COMBINATION
 - windot11/_DOT11_VWIFI_COMBINATION
 - PDOT11_VWIFI_COMBINATION
 - windot11/PDOT11_VWIFI_COMBINATION
 - DOT11_VWIFI_COMBINATION
 - windot11/DOT11_VWIFI_COMBINATION
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - windot11.h
api_name:
 - _DOT11_VWIFI_COMBINATION
 - PDOT11_VWIFI_COMBINATION
 - DOT11_VWIFI_COMBINATION
---

# _DOT11_VWIFI_COMBINATION structure


## -description

> [!Important]
> [WiFiCx](/windows-hardware/drivers/netcx/wifi-wdf-class-extension-wificx) is the new Wi-Fi driver model released in Windows 11. We recommend that you use WiFiCx to take advantage of the latest features. The WDI driver model is now in maintenance mode and will only receive high priority fixes.

The DOT11_VWIFI_COMBINATION structure specifies the combination of 802.11 MAC entities that an 802.11
  miniport driver can simultaneously support when it is virtualized.

## -struct-fields

### -field Header

The type, revision, and size of the DOT11_VWIFI_COMBINATION structure. This member is formatted as
     an
     <a href="..\objectheader\ns-objectheader-ndis_object_header.md">NDIS_OBJECT_HEADER</a> structure.


The miniport driver must set the members of
     <b>Header</b> to the following values:





#### Type

This member must be set to NDIS_OBJECT_TYPE_DEFAULT.



#### Revision

This member must be set to DOT11_VWIFI_COMBINATION_REVISION_1.



#### Size

This member must be set to
       sizeof(DOT11_VWIFI_COMBINATION).

For more information about these members, see
     <a href="..\objectheader\ns-objectheader-ndis_object_header.md">NDIS_OBJECT_HEADER</a>.

### -field uNumInfrastructure

The number of 802.11 infrastructure stations supported. For more information, see the following
     Remarks section.

### -field uNumAdhoc

The number of Adhoc Stations supported. For more information, see the following Remarks
     section.

### -field uNumSoftAP

The number of Soft AP Stations supported. For more information, see the following Remarks
     section.

## -syntax

```cpp
typedef struct _DOT11_VWIFI_COMBINATION {
  NDIS_OBJECT_HEADER Header;
  ULONG              uNumInfrastructure;
  ULONG              uNumAdhoc;
  ULONG              uNumSoftAP;
} DOT11_VWIFI_COMBINATION, *PDOT11_VWIFI_COMBINATION;
```

## -remarks

Starting with Windows 7, the 802.11 miniport driver must only report one or more of the following
    combination of member values.

<ul>
<li>
<b>uNumInfrastructure</b> = 1

</li>
<li>
<b>uNumAdhoc</b> = 0

</li>
<li>
<b>uNumSoftAP</b> = 1

</li>
</ul>

## -see-also

<a href="..\objectheader\ns-objectheader-ndis_object_header.md">NDIS_OBJECT_HEADER</a>


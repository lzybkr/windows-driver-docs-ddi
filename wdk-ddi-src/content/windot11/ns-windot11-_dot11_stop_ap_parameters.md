---
UID: NS:windot11._DOT11_STOP_AP_PARAMETERS
title: _DOT11_STOP_AP_PARAMETERS (windot11.h)
description: The DOT11_STOP_AP_PARAMETERS structure is part of the Native 802.11 Wireless LAN interface, which is deprecated for Windows 10 and later.
old-location: netvista\dot11_stop_ap_parameters.htm
tech.root: netvista
ms.date: 02/16/2018
keywords: ["DOT11_STOP_AP_PARAMETERS structure"]
ms.keywords: "*PDOT11_STOP_AP_PARAMETERS, DOT11_STOP_AP_PARAMETERS, DOT11_STOP_AP_PARAMETERS structure [Network Drivers Starting with Windows Vista], Native_802.11_data_types_1c8e69b9-852b-4ad6-87a4-ae13b37f7523.xml, PDOT11_STOP_AP_PARAMETERS, PDOT11_STOP_AP_PARAMETERS structure pointer [Network Drivers Starting with Windows Vista], _DOT11_STOP_AP_PARAMETERS, netvista.dot11_stop_ap_parameters, windot11/DOT11_STOP_AP_PARAMETERS, windot11/PDOT11_STOP_AP_PARAMETERS"
req.header: windot11.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows 7 and later versions of the Windows operating   system.
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
req.typenames: DOT11_STOP_AP_PARAMETERS, *PDOT11_STOP_AP_PARAMETERS
f1_keywords:
 - _DOT11_STOP_AP_PARAMETERS
 - windot11/_DOT11_STOP_AP_PARAMETERS
 - PDOT11_STOP_AP_PARAMETERS
 - windot11/PDOT11_STOP_AP_PARAMETERS
 - DOT11_STOP_AP_PARAMETERS
 - windot11/DOT11_STOP_AP_PARAMETERS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - windot11.h
api_name:
 - _DOT11_STOP_AP_PARAMETERS
 - PDOT11_STOP_AP_PARAMETERS
 - DOT11_STOP_AP_PARAMETERS
---

# _DOT11_STOP_AP_PARAMETERS structure


## -description

> [!Important]
> [WiFiCx](/windows-hardware/drivers/netcx/wifi-wdf-class-extension-wificx) is the new Wi-Fi driver model released in Windows 11. We recommend that you use WiFiCx to take advantage of the latest features. The WDI driver model is now in maintenance mode and will only receive high priority fixes.

The DOT11_STOP_AP_PARAMETERS structure specifies the reason why the NIC has stopped an 802.11 access
  point (AP).

## -struct-fields

### -field Header

The type, revision, and size of the DOT11_STOP_AP_PARAMETERS structure. This member is formatted
     as an
     <a href="..\objectheader\ns-objectheader-ndis_object_header.md">NDIS_OBJECT_HEADER</a> structure.


The miniport driver must set the members of
     <b>Header</b> to the following values:





#### Type

This member must be set to NDIS_OBJECT_TYPE_DEFAULT.



#### Revision

This member must be set to DOT11_STOP_AP_PARAMETERS_REVISION_1.



#### Size

This member must be set to
       sizeof(DOT11_STOP_AP_PARAMETERS).

For more information about these members, see
     <a href="..\objectheader\ns-objectheader-ndis_object_header.md">NDIS_OBJECT_HEADER</a>.

### -field ulReason

The reason why the NIC stopped the AP. An IHV can supply the following range of values:






#### DOT11_STOP_AP_REASON_AP_ACTIVE

The miniport driver determined that an AP is already active on another 802.11 MAC entity for
       this physical wireless LAN adapter.



#### DOT11_STOP_AP_REASON_CHANNEL_NOT_AVAILABLE

The miniport driver determined that no valid operating frequency is available.



#### DOT11_STOP_AP_REASON_FREQUENCY_NOT_AVAILABLE

The miniport driver determined that no good operating channel is available.



#### DOT11_STOP_AP_REASON_IHV_END

The end value of possible IHV-specified reasons.



#### DOT11_STOP_AP_REASON_IHV_START

The start value of possible IHV-specified reasons.

If the value of
     <b>ulReason</b> is in the range of DOT11_STOP_AP_REASON_IHV_START and DOT11_STOP_AP_REASON_IHV_END,
     inclusive, the operating system takes no action.

## -syntax

```cpp
typedef struct _DOT11_STOP_AP_PARAMETERS {
  NDIS_OBJECT_HEADER Header;
  ULONG              ulReason;
} DOT11_STOP_AP_PARAMETERS, *PDOT11_STOP_AP_PARAMETERS;
```

## -remarks

The Native 802.11 miniport driver includes a DOT11_STOP_AP_PARAMETERS structure when the driver makes
    an
    <a href="/windows-hardware/drivers/network/ndis-status-dot11-stop-ap">NDIS_STATUS_DOT11_STOP_AP</a> status
    indication.

## -see-also

<a href="/windows-hardware/drivers/network/ndis-status-dot11-stop-ap">NDIS_STATUS_DOT11_STOP_AP</a>



<a href="..\objectheader\ns-objectheader-ndis_object_header.md">NDIS_OBJECT_HEADER</a>


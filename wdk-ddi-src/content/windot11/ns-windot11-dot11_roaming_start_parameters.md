---
UID: NS:windot11.DOT11_ROAMING_START_PARAMETERS
title: DOT11_ROAMING_START_PARAMETERS (windot11.h)
description: The DOT11_ROAMING_START_PARAMETERS structure is part of the Native 802.11 Wireless LAN interface, which is deprecated for Windows 10 and later.
old-location: netvista\dot11_roaming_start_parameters.htm
tech.root: netvista
ms.date: 02/16/2018
keywords: ["DOT11_ROAMING_START_PARAMETERS structure"]
ms.keywords: "*PDOT11_ROAMING_START_PARAMETERS, DOT11_ROAMING_START_PARAMETERS, DOT11_ROAMING_START_PARAMETERS structure [Network Drivers Starting with Windows Vista], Native_802.11_data_types_7635397d-74dc-44d0-af58-47048361367d.xml, PDOT11_ROAMING_START_PARAMETERS, PDOT11_ROAMING_START_PARAMETERS structure pointer [Network Drivers Starting with Windows Vista], netvista.dot11_roaming_start_parameters, windot11/DOT11_ROAMING_START_PARAMETERS, windot11/PDOT11_ROAMING_START_PARAMETERS"
req.header: windot11.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating   systems.
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
req.typenames: DOT11_ROAMING_START_PARAMETERS, *PDOT11_ROAMING_START_PARAMETERS
f1_keywords:
 - DOT11_ROAMING_START_PARAMETERS
 - windot11/DOT11_ROAMING_START_PARAMETERS
 - PDOT11_ROAMING_START_PARAMETERS
 - windot11/PDOT11_ROAMING_START_PARAMETERS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - windot11.h
api_name:
 - DOT11_ROAMING_START_PARAMETERS
 - PDOT11_ROAMING_START_PARAMETERS
---

# DOT11_ROAMING_START_PARAMETERS structure


## -description

> [!Important]
> [WiFiCx](/windows-hardware/drivers/netcx/wifi-wdf-class-extension-wificx) is the new Wi-Fi driver model released in Windows 11. We recommend that you use WiFiCx to take advantage of the latest features. The WDI driver model is now in maintenance mode and will only receive high priority fixes.

The DOT11_ROAMING_START_PARAMETERS structure specifies the reason why the Native 802.11 miniport
  driver is performing a roaming operation. The driver includes a DOT11_ROAMING_START_PARAMETERS structure
  when the driver makes an
  <a href="/windows-hardware/drivers/network/ndis-status-dot11-roaming-start">
  NDIS_STATUS_DOT11_ROAMING_START</a> status indication.

## -struct-fields

### -field Header

The type, revision, and size of the DOT11_ROAMING_START_PARAMETERS structure. This member is
     formatted as an
     <a href="..\objectheader\ns-objectheader-ndis_object_header.md">NDIS_OBJECT_HEADER</a> structure.


The miniport driver must set the members of
     <b>Header</b> to the following values:





#### Type

This member must be set to NDIS_OBJECT_TYPE_DEFAULT.



#### Revision

This member must be set to DOT11_ROAMING_START_PARAMETERS_REVISION_1.



#### Size

This member must be set to
       sizeof(DOT11_ROAMING_START_PARAMETERS).

For more information about these members, see
     <a href="..\objectheader\ns-objectheader-ndis_object_header.md">NDIS_OBJECT_HEADER</a>.

### -field AdhocBSSID

If the IEEE 802.11
     <b>dot11DesiredBSSType</b> MIB object is set to
     <b>dot11_BSS_type_independent</b>, the
     <b>AdhocBSSID</b> member contains the basic service set (BSS) identifier (BSSID) of the independent BSS
     (IBSS) network that the 802.11 station is attempting to roam to.

<div class="alert"><b>Note</b>  IBSS (Ad hoc) and SoftAP are deprecated. Starting with Windows 8.1 and Windows Server 2012 R2, use <a href="/windows-hardware/drivers/partnerapps/wi-fi-direct">Wi-Fi Direct</a>.</div>
<div> </div>
If the
     <b>dot11DesiredBSSType</b> MIB object is set to
     <b>dot11_BSS_type_infrastructure</b>, the miniport driver must fill
     <b>AdhocBSSID</b> with zeros.

For more information about the data type for this member, see
     <a href="..\windot11\ns-windot11-_dot11_mac_address.md">DOT11_MAC_ADDRESS</a>.

### -field AdhocSSID

If the
     <b>dot11DesiredBSSType</b> MIB object is set to
     <b>dot11_BSS_type_independent</b>, the
     <b>AdhocSSID</b> member contains the service set identifier (SSID) of the IBSS network that the 802.11
     station is attempting to roam to.

<div class="alert"><b>Note</b>  IBSS (Ad hoc) and SoftAP are deprecated. Starting with Windows 8.1 and Windows Server 2012 R2, use <a href="/windows-hardware/drivers/partnerapps/wi-fi-direct">Wi-Fi Direct</a>.</div>
<div> </div>
If the
     <b>dot11DesiredBSSType</b> MIB object is set to
     <b>dot11_BSS_type_infrastructure</b>, the miniport driver must fill
     <b>AdhocSSID</b> with zeros.

For more information about the data type for this member, see
     <a href="..\wlantypes\ns-wlantypes-_dot11_ssid.md">DOT11_SSID</a>.

For more information about the IEEE 802.11
     <b>dot11DesiredBSSType</b> MIB object, see
     <a href="/windows-hardware/drivers/network/oid-dot11-desired-bss-type">
     OID_DOT11_DESIRED_BSS_TYPE</a>.

### -field uRoamingReason

The reason that the 802.11 station is roaming, which is formatted as a
     <a href="/windows-hardware/drivers/network/dot11-assoc-status-status-codes">DOT11_ASSOC_STATUS</a> value.

## -syntax

```cpp
typedef struct DOT11_ROAMING_START_PARAMETERS {
  NDIS_OBJECT_HEADER Header;
  DOT11_MAC_ADDRESS  AdhocBSSID;
  DOT11_SSID         AdhocSSID;
  DOT11_ASSOC_STATUS uRoamingReason;
} DOT11_ROAMING_START_PARAMETERS, *PDOT11_ROAMING_START_PARAMETERS;
```

## -remarks

For more information about the roaming operation, see
    <a href="/windows-hardware/drivers/network/roaming-operations">Roaming Operations</a>.

## -see-also

<a href="/windows-hardware/drivers/network/dot11-assoc-status-status-codes">DOT11_ASSOC_STATUS</a>



<a href="..\wlantypes\ns-wlantypes-_dot11_ssid.md">DOT11_SSID</a>



<a href="..\windot11\ns-windot11-_dot11_mac_address.md">DOT11_MAC_ADDRESS</a>



<a href="/windows-hardware/drivers/network/oid-dot11-desired-bss-type">OID_DOT11_DESIRED_BSS_TYPE</a>



<a href="/windows-hardware/drivers/network/ndis-status-dot11-roaming-start">NDIS_STATUS_DOT11_ROAMING_START</a>



<a href="..\objectheader\ns-objectheader-ndis_object_header.md">NDIS_OBJECT_HEADER</a>


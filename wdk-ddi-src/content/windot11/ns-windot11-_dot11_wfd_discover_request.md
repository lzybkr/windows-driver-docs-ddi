---
UID: NS:windot11._DOT11_WFD_DISCOVER_REQUEST
title: _DOT11_WFD_DISCOVER_REQUEST (windot11.h)
description: The OID_DOT11_WFD_DISCOVER_REQUEST structure is the input data for an OID_DOT11_WFD_DISCOVER_REQUEST request. The structure contains the parameters for a Wi-Fi Direct device discovery.
old-location: netvista\_dot11_wfd_discover_request.htm
tech.root: netvista
ms.date: 02/16/2018
keywords: ["DOT11_WFD_DISCOVER_REQUEST structure"]
ms.keywords: "*PDOT11_WFD_DISCOVER_REQUEST, DOT11_WFD_DISCOVER_REQUEST, DOT11_WFD_DISCOVER_REQUEST structure [Network Drivers Starting with Windows Vista], PDOT11_WFD_DISCOVER_REQUEST, PDOT11_WFD_DISCOVER_REQUEST structure pointer [Network Drivers Starting with Windows Vista], _DOT11_WFD_DISCOVER_REQUEST, netvista._dot11_wfd_discover_request, windot11/ DOT11_WFD_DISCOVER_REQUEST, windot11/PDOT11_WFD_DISCOVER_REQUEST"
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
req.typenames: DOT11_WFD_DISCOVER_REQUEST, *PDOT11_WFD_DISCOVER_REQUEST
f1_keywords:
 - _DOT11_WFD_DISCOVER_REQUEST
 - windot11/_DOT11_WFD_DISCOVER_REQUEST
 - PDOT11_WFD_DISCOVER_REQUEST
 - windot11/PDOT11_WFD_DISCOVER_REQUEST
 - DOT11_WFD_DISCOVER_REQUEST
 - windot11/DOT11_WFD_DISCOVER_REQUEST
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Windot11.h
api_name:
 - _DOT11_WFD_DISCOVER_REQUEST
 - PDOT11_WFD_DISCOVER_REQUEST
 - DOT11_WFD_DISCOVER_REQUEST
---

# _DOT11_WFD_DISCOVER_REQUEST structure


## -description

> [!Important]
> [WiFiCx](/windows-hardware/drivers/netcx/wifi-wdf-class-extension-wificx) is the new Wi-Fi driver model released in Windows 11. We recommend that you use WiFiCx to take advantage of the latest features. The WDI driver model is now in maintenance mode and will only receive high priority fixes.

The <b>OID_DOT11_WFD_DISCOVER_REQUEST</b> structure is the input  data for an <a href="/windows-hardware/drivers/network/oid-dot11-wfd-discover-request">OID_DOT11_WFD_DISCOVER_REQUEST</a> request.  The structure contains the parameters for a Wi-Fi Direct device discovery.

## -struct-fields

### -field Header

The type, revision, and size of the<b>OID_DOT11_WFD_DISCOVER_REQUEST</b> structure. This member is formatted as an
     <a href="..\objectheader\ns-objectheader-ndis_object_header.md">NDIS_OBJECT_HEADER</a> structure.


The miniport driver must set the members of
     <b>Header</b> to the following values:





#### Type

This member must be set to <b>NDIS_OBJECT_TYPE_DEFAULT</b>.



#### Revision

This member must be set to <b>DOT11_WFD_DISCOVER_REQUEST_REVISION_1</b>.



#### Size

This member must be set to
       <b>sizeof</b>(<b>DOT11_SIZEOF_WFD_DISCOVER_REQUEST_REVISION_1</b>).

For more information about these members, see
     <a href="..\objectheader\ns-objectheader-ndis_object_header.md">NDIS_OBJECT_HEADER</a>.

### -field DiscoverType

The device discovery mode to use.

### -field ScanType

Scanning type used during the scan phase of device discovery.

### -field uDiscoverTimeout

Maximum time, in milliseconds, to complete the discovery operation. A miniport can complete a discovery in less time, however, it should not use any more time than specified by this value. This is the total time allowed for completion of all phases of device discovery.

### -field uDeviceFilterListOffset

The offset to the list of P2P Device filters, which specifies the P2P devices and Group Owners to search for during Wi-Fi Direct device discovery. This offset is specified in bytes and is relative to the start of the buffer that contains the DOT11_WFD_DISCOVER_REQUEST structure. Each entry in the list is formatted as a DOT11_WFD_DISCOVER_DEVICE_FILTER.

When a list entry specifies a non-broadcast MAC address as the Device ID, the driver must use this MAC address in the Device ID Attribute of the P2P IEs it includes in the probe requests.

The offset in the <b>InformationBuffer</b> of the <a href="..\oidrequest\ns-oidrequest-ndis_oid_request.md">NDIS_OID_REQUEST</a> where a list of P2P device identifiers begins. These are the identifiers to for during device discovery.

### -field uNumDeviceFilters

The number of P2P device filters to use during WFD device discovery. The default value for this field is 0.

### -field uIEsOffset

The offset in the <b>InformationBuffer</b> of the <a href="..\oidrequest\ns-oidrequest-ndis_oid_request.md">NDIS_OID_REQUEST</a> structure where the additional Informational Elements (IEs) begin.

### -field uIEsLength

The length, in bytes, of the additional IEs which the Wi-Fi Direct device port must add to the probe request packet. If this value is 0, the system did not provide any IEs and the miniport must insert the  default IEs in the probe request packet. The default IEs are in  <b>DefaultRequestIEs</b> received earlier with an <a href="/windows-hardware/drivers/network/oid-dot11-wfd-additional-ie">OID_DOT11_WFD_ADDITIONAL_IE</a> request.

### -field bForceScanLegacyNetworks

When TRUE, the Wi-Fi Direct device must also attempt to discover legacy networks. Otherwise, scanning for legacy networks is not necessary.

## -syntax

```cpp
typedef struct _DOT11_WFD_DISCOVER_REQUEST {
  NDIS_OBJECT_HEADER      Header;
  DOT11_WFD_DISCOVER_TYPE DiscoverType;
  DOT11_WFD_SCAN_TYPE     ScanType;
  ULONG                   uDiscoverTimeout;
  ULONG                   uDeviceFilterListOffset;
  ULONG                   uNumDeviceFilters;
  ULONG                   uIEsOffset;
  ULONG                   uIEsLength;
  BOOLEAN                 bForceScanLegacyNetworks;
} DOT11_WFD_DISCOVER_REQUEST, *PDOT11_WFD_DISCOVER_REQUEST;
```

## -remarks

Each entry in the device identifier list at <b>uDeviceFilterListOffset</b> is formatted as a <a href="..\windot11\ns-windot11-_dot11_mac_address.md">DOT11_MAC_ADDRESS</a> structure. When a non-broadcast MAC address is specified in this list, the driver must use this address in the Device ID attribute of the P2P IEs probe requests it transmits

The IEs present at <b>uIEsOffset</b>, for the duration of the device discovery, will temporarily replace IEs found at <b>DefaultRequestIEs</b> in input structure of the <a href="/windows-hardware/drivers/network/oid-dot11-wfd-additional-ie">OID_DOT11_WFD_ADDITIONAL_IE</a> request.

## -see-also

<a href="/windows-hardware/drivers/network/oid-dot11-wfd-discover-request">OID_DOT11_WFD_DISCOVER_REQUEST</a>



<a href="..\windot11\ne-windot11-_dot11_wfd_scan_type.md">DOT11_WFD_SCAN_TYPE</a>



<a href="..\windot11\ne-windot11-_dot11_wfd_discover_type.md">DOT11_WFD_DISCOVER_TYPE</a>



<a href="..\objectheader\ns-objectheader-ndis_object_header.md">NDIS_OBJECT_HEADER</a>


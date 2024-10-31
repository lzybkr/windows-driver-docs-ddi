---
UID: NS:windot11._DOT11_PEER_INFO_LIST
title: _DOT11_PEER_INFO_LIST (windot11.h)
description: The DOT11_PEER_INFO_LIST structure is part of the Native 802.11 Wireless LAN interface, which is deprecated for Windows 10 and later.
old-location: netvista\dot11_peer_info_list.htm
tech.root: netvista
ms.date: 02/16/2018
keywords: ["DOT11_PEER_INFO_LIST structure"]
ms.keywords: "*PDOT11_PEER_INFO_LIST, DOT11_PEER_INFO_LIST, DOT11_PEER_INFO_LIST structure [Network Drivers Starting with Windows Vista], Native_802.11_data_types_c969625e-444f-4741-a284-6bd77253c8b9.xml, PDOT11_PEER_INFO_LIST, PDOT11_PEER_INFO_LIST structure pointer [Network Drivers Starting with Windows Vista], _DOT11_PEER_INFO_LIST, netvista.dot11_peer_info_list, windot11/DOT11_PEER_INFO_LIST, windot11/PDOT11_PEER_INFO_LIST"
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
req.typenames: DOT11_PEER_INFO_LIST, *PDOT11_PEER_INFO_LIST
f1_keywords:
 - _DOT11_PEER_INFO_LIST
 - windot11/_DOT11_PEER_INFO_LIST
 - PDOT11_PEER_INFO_LIST
 - windot11/PDOT11_PEER_INFO_LIST
 - DOT11_PEER_INFO_LIST
 - windot11/DOT11_PEER_INFO_LIST
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - windot11.h
api_name:
 - _DOT11_PEER_INFO_LIST
 - PDOT11_PEER_INFO_LIST
 - DOT11_PEER_INFO_LIST
---

# _DOT11_PEER_INFO_LIST structure


## -description

> [!Important]
> [WiFiCx](/windows-hardware/drivers/netcx/wifi-wdf-class-extension-wificx) is the new Wi-Fi driver model released in Windows 11. We recommend that you use WiFiCx to take advantage of the latest features. The WDI driver model is now in maintenance mode and will only receive high priority fixes.

The DOT11_PEER_INFO_LIST structure specifies a list of <a href="..\windot11\ns-windot11-_dot11_peer_info.md">DOT11_PEER_INFO</a> structures that specify information about all peer stations within an independent basic service set (IBSS) network.

<div class="alert"><b>Note</b>  IBSS (Ad hoc) and SoftAP are deprecated. Starting with Windows 8.1 and Windows Server 2012 R2, use <a href="/windows-hardware/drivers/partnerapps/wi-fi-direct">Wi-Fi Direct</a>.</div>

## -struct-fields

### -field Header

The type, revision, and size of the DOT11_PEER_INFO_LIST structure. This member is formatted as an <a href="..\objectheader\ns-objectheader-ndis_object_header.md">NDIS_OBJECT_HEADER</a> structure.

The miniport driver must set the members of <b>Header</b> to the following values:

#### Type

This member must be set to NDIS_OBJECT_TYPE_DEFAULT.



#### Revision

This member must be set to DOT11_PEER_INFO_LIST_REVISION_1.



#### Size

This member must be set to
       sizeof(DOT11_PEER_INFO_LIST).

For more information about these members, see
     <a href="..\objectheader\ns-objectheader-ndis_object_header.md">NDIS_OBJECT_HEADER</a>.

### -field uNumOfEntries

The number of entries in the
     <b>PeerInfo</b> array.

### -field uTotalNumOfEntries

The maximum number of entries that the
     <b>PeerInfo</b> array can contain.

### -field PeerInfo

An array that specifies the list of
     <a href="..\windot11\ns-windot11-_dot11_peer_info.md">DOT11_PEER_INFO</a> structures that specify
     information on all peer stations within an IBSS network. Each station is represented by a
     DOT11_PEER_INFO structure.

## -syntax

```cpp
typedef struct _DOT11_PEER_INFO_LIST {
  NDIS_OBJECT_HEADER Header;
  ULONG              uNumOfEntries;
  ULONG              uTotalNumOfEntries;
  DOT11_PEER_INFO    PeerInfo[1];
} DOT11_PEER_INFO_LIST, *PDOT11_PEER_INFO_LIST;
```

## -remarks

This structure is used with
    <a href="/windows-hardware/drivers/network/oid-dot11-enum-peer-info">OID_DOT11_ENUM_PEER_INFO</a>.

## -see-also

<a href="/windows-hardware/drivers/network/oid-dot11-enum-peer-info">OID_DOT11_ENUM_PEER_INFO</a>



<a href="..\windot11\ns-windot11-_dot11_peer_info.md">DOT11_PEER_INFO</a>



<a href="..\objectheader\ns-objectheader-ndis_object_header.md">NDIS_OBJECT_HEADER</a>


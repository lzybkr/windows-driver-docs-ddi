---
UID: NS:windot11.DOT11_ENCAP_ENTRY
title: DOT11_ENCAP_ENTRY (windot11.h)
description: The DOT11_ENCAP_ENTRY structure is part of the Native 802.11 Wireless LAN interface, which is deprecated for Windows 10 and later.
old-location: netvista\dot11_encap_entry.htm
tech.root: netvista
ms.date: 02/16/2018
keywords: ["DOT11_ENCAP_ENTRY structure"]
ms.keywords: "*PDOT11_ENCAP_ENTRY, DOT11_ENCAP_ENTRY, DOT11_ENCAP_ENTRY structure [Network Drivers Starting with Windows Vista], Native_802.11_data_types_3304c37a-c08f-488e-a75d-d31d59a4a491.xml, PDOT11_ENCAP_ENTRY, PDOT11_ENCAP_ENTRY structure pointer [Network Drivers Starting with Windows Vista], netvista.dot11_encap_entry, windot11/DOT11_ENCAP_ENTRY, windot11/PDOT11_ENCAP_ENTRY"
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
req.typenames: DOT11_ENCAP_ENTRY, *PDOT11_ENCAP_ENTRY
f1_keywords:
 - DOT11_ENCAP_ENTRY
 - windot11/DOT11_ENCAP_ENTRY
 - PDOT11_ENCAP_ENTRY
 - windot11/PDOT11_ENCAP_ENTRY
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - windot11.h
api_name:
 - DOT11_ENCAP_ENTRY
 - PDOT11_ENCAP_ENTRY
---

# DOT11_ENCAP_ENTRY structure


## -description

> [!Important]
> [WiFiCx](/windows-hardware/drivers/netcx/wifi-wdf-class-extension-wificx) is the new Wi-Fi driver model released in Windows 11. We recommend that you use WiFiCx to take advantage of the latest features. The WDI driver model is now in maintenance mode and will only receive high priority fixes.

The DOT11_ENCAP_ENTRY structure defines an encapsulation type to be applied to the payload of an
  802.11 packet based on the packet's IEEE EtherType.

## -struct-fields

### -field usEtherType

The value of the IEEE EtherType in big-endian byte order.


If the
     <b>usEtherType</b> member is zero, the encapsulation that is specified by the
     <b>usEncapType</b> member applies to all EtherType values. If the miniport driver sets
     <b>usEtherType</b> to zero for an entry, it must be the only entry in the EtherType encapsulation
     list.

### -field usEncapType

The type of encapsulation that is performed on the EtherType specified by the
     <b>usEtherType</b> member. The
     <b>usEncapType</b> member can have one of the following values:






#### DOT11_ENCAP_RFC_1042

The encapsulation that is defined through IETF RFC 1042.



#### DOT11_ENCAP_802_IH

The encapsulation that is defined through the IEEE 802.1h-1997 standard.

## -syntax

```cpp
typedef struct DOT11_ENCAP_ENTRY {
  USHORT usEtherType;
  USHORT usEncapType;
} DOT11_ENCAP_ENTRY, *PDOT11_ENCAP_ENTRY;
```

## -remarks

The miniport driver returns an encapsulation list when it makes an
    <a href="/windows-hardware/drivers/network/ndis-status-dot11-association-completion">
    NDIS_STATUS_DOT11_ASSOCIATION_COMPLETION</a> indication. The encapsulation list specified in the
    indication applies to the association with an access point (AP) in an infrastructure basic service set
    (BSS) network.

<div class="alert"><b>Note</b>  The miniport driver cannot return an encapsulation list when associating with peer
    stations within an independent BSS network.</div>
<div> </div>
For more information about 802.11 packet payload encapsulation, see
    <a href="/previous-versions/windows/it-pro/windows-server-2003/cc757419(v=ws.10)">802.11 Payload Encapsulation</a>.

## -see-also

<a href="/windows-hardware/drivers/network/ndis-status-dot11-association-completion">
   NDIS_STATUS_DOT11_ASSOCIATION_COMPLETION</a>



<a href="..\windot11\ns-windot11-dot11_association_completion_parameters.md">
   DOT11_ASSOCIATION_COMPLETION_PARAMETERS</a>


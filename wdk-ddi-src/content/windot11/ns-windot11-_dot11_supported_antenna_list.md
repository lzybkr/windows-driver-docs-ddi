---
UID: NS:windot11._DOT11_SUPPORTED_ANTENNA_LIST
title: _DOT11_SUPPORTED_ANTENNA_LIST (windot11.h)
description: The DOT11_SUPPORTED_ANTENNA_LIST structure is part of the Native 802.11 Wireless LAN interface, which is deprecated for Windows 10 and later.
old-location: netvista\dot11_supported_antenna_list.htm
tech.root: netvista
ms.date: 02/16/2018
keywords: ["DOT11_SUPPORTED_ANTENNA_LIST structure"]
ms.keywords: "*PDOT11_SUPPORTED_ANTENNA_LIST, DOT11_SUPPORTED_ANTENNA_LIST, DOT11_SUPPORTED_ANTENNA_LIST structure [Network Drivers Starting with Windows Vista], Native_802.11_data_types_5e735315-0745-4395-bf71-fe53a941daf8.xml, PDOT11_SUPPORTED_ANTENNA_LIST, PDOT11_SUPPORTED_ANTENNA_LIST structure pointer [Network Drivers Starting with Windows Vista], _DOT11_SUPPORTED_ANTENNA_LIST, netvista.dot11_supported_antenna_list, windot11/DOT11_SUPPORTED_ANTENNA_LIST, windot11/PDOT11_SUPPORTED_ANTENNA_LIST"
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
req.typenames: DOT11_SUPPORTED_ANTENNA_LIST, *PDOT11_SUPPORTED_ANTENNA_LIST
f1_keywords:
 - _DOT11_SUPPORTED_ANTENNA_LIST
 - windot11/_DOT11_SUPPORTED_ANTENNA_LIST
 - PDOT11_SUPPORTED_ANTENNA_LIST
 - windot11/PDOT11_SUPPORTED_ANTENNA_LIST
 - DOT11_SUPPORTED_ANTENNA_LIST
 - windot11/DOT11_SUPPORTED_ANTENNA_LIST
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - windot11.h
api_name:
 - _DOT11_SUPPORTED_ANTENNA_LIST
 - PDOT11_SUPPORTED_ANTENNA_LIST
 - DOT11_SUPPORTED_ANTENNA_LIST
---

# _DOT11_SUPPORTED_ANTENNA_LIST structure


## -description

> [!Important]
> [WiFiCx](/windows-hardware/drivers/netcx/wifi-wdf-class-extension-wificx) is the new Wi-Fi driver model released in Windows 11. We recommend that you use WiFiCx to take advantage of the latest features. The WDI driver model is now in maintenance mode and will only receive high priority fixes.

The DOT11_SUPPORTED_ANTENNA_LIST structure specifies a list of antennas that can be used for receive
  or transmit operations.

## -struct-fields

### -field uNumOfEntries

The number of entries in the
     <b>dot11SupportedAntenna</b> array. A zero value for the
     <b>uNumOfEntries</b> member indicates an empty list.

### -field uTotalNumOfEntries

The maximum number of entries that the
     <b>dot11SupportedAntenna</b> array can contain.

### -field dot11SupportedAntenna

The list of supported antennas. Each element in this list is formatted as a
     <a href="..\windot11\ns-windot11-_dot11_supported_antenna.md">
     DOT11_SUPPORTED_ANTENNA</a> structure.

## -syntax

```cpp
typedef struct _DOT11_SUPPORTED_ANTENNA_LIST {
  ULONG                   uNumOfEntries;
  ULONG                   uTotalNumOfEntries;
  DOT11_SUPPORTED_ANTENNA dot11SupportedAntenna[1];
} DOT11_SUPPORTED_ANTENNA_LIST, *PDOT11_SUPPORTED_ANTENNA_LIST;
```

## -remarks

A miniport driver returns the DOT11_SUPPORTED_ANTENNA_LIST structure when queried by either
    <a href="/previous-versions/ms893804(v=msdn.10)">
    OID_DOT11_SUPPORTED_RX_ANTENNA</a> or
    <a href="/previous-versions/windows/embedded/ee484405(v=winembedded.80)">
    OID_DOT11_SUPPORTED_TX_ANTENNA</a>.

When these OIDs are queried, the miniport driver must verify that the
    <b>InformationBuffer</b> member of the
    <a href="..\ndis\nc-ndis-miniport_oid_request.md">MiniportOidRequest</a> function's
    <i>OidRequest</i> parameter is large enough to return the entire DOT11_SUPPORTED_ANTENNA_LIST structure,
    including all entries in the
    <b>dot11SupportedAntenna</b> array. The value of the
    <b>InformationBufferLength</b> member of the
    <i>OidRequest</i> parameter determines what the miniport driver must do, as the following list shows:

<ul>
<li>
If the value of the
      <b>InformationBufferLength</b> member is less than the length, in bytes, of the entire
      DOT11_SUPPORTED_ANTENNA_LIST structure, the miniport driver must do the following:

<ul>
<li>
Set the
        <b>uNumOfEntries</b> member to zero.

</li>
<li>
Set the
        <b>uTotalNumOfEntries</b> member to the number of entries in the
        <b>dot11SupportedAntenna</b> array.

For the
        <i>OidRequest</i> parameter, set the
        <b>BytesWritten</b> member to zero and the
        <b>BytesNeeded</b> member to the length, in bytes, of the entire DOT11_PHY_ID_LIST structure.

</li>
<li>
Fail the query request by returning NDIS_STATUS_BUFFER_OVERFLOW from its
        <a href="..\ndis\nc-ndis-miniport_oid_request.md">MiniportOidRequest</a> function.

</li>
</ul>
</li>
<li>
If the value of the
      <b>InformationBufferLength</b> member is greater than or equal to the length, in bytes, of the entire
      DOT11_SUPPORTED_ANTENNA_LIST structure, the miniport driver must do the following to complete a
      successful query request:

<ul>
<li>
For the DOT11_SUPPORTED_ANTENNA_LIST structure, set the
        <b>uNumOfEntries</b> and
        <b>uTotalNumOfEntries</b> members to the total number of entries in the
        <b>dot11SupportedAntenna</b> array.

</li>
<li>
For the
        <i>OidRequest</i> parameter, set the
        <b>BytesNeeded</b> member to zero and the
        <b>BytesWritten</b> member to the length, in bytes, of the entire DOT11_SUPPORTED_ANTENNA_LIST
        structure. The miniport driver must also copy the entire DOT11_SUPPORTED_ANTENNA_LIST structure to
        the
        <b>InformationBuffer</b> member.

</li>
<li>
Return NDIS_STATUS_SUCCESS from its
        <a href="..\ndis\nc-ndis-miniport_oid_request.md">MiniportOidRequest</a> function.

</li>
</ul>
</li>
</ul>

## -see-also

<a href="..\windot11\ns-windot11-_dot11_supported_antenna.md">DOT11_SUPPORTED_ANTENNA</a>



<a href="/previous-versions/windows/embedded/ee484405(v=winembedded.80)">OID_DOT11_SUPPORTED_TX_ANTENNA</a>



<a href="/previous-versions/ms893804(v=msdn.10)">OID_DOT11_SUPPORTED_RX_ANTENNA</a>


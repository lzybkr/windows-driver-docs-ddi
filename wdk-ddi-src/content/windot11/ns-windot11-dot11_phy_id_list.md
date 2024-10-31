---
UID: NS:windot11.DOT11_PHY_ID_LIST
title: DOT11_PHY_ID_LIST (windot11.h)
description: The DOT11_PHY_ID_LIST structure is part of the Native 802.11 Wireless LAN interface, which is deprecated for Windows 10 and later.
old-location: netvista\dot11_phy_id_list.htm
tech.root: netvista
ms.date: 02/16/2018
keywords: ["DOT11_PHY_ID_LIST structure"]
ms.keywords: "*PDOT11_PHY_ID_LIST, DOT11_PHY_ID_LIST, DOT11_PHY_ID_LIST structure [Network Drivers Starting with Windows Vista], Native_802.11_data_types_e6b82eab-cd00-460f-8956-9b1c8cf86be1.xml, PDOT11_PHY_ID_LIST, PDOT11_PHY_ID_LIST structure pointer [Network Drivers Starting with Windows Vista], netvista.dot11_phy_id_list, windot11/DOT11_PHY_ID_LIST, windot11/PDOT11_PHY_ID_LIST"
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
req.typenames: DOT11_PHY_ID_LIST, *PDOT11_PHY_ID_LIST
f1_keywords:
 - DOT11_PHY_ID_LIST
 - windot11/DOT11_PHY_ID_LIST
 - PDOT11_PHY_ID_LIST
 - windot11/PDOT11_PHY_ID_LIST
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - windot11.h
api_name:
 - DOT11_PHY_ID_LIST
 - PDOT11_PHY_ID_LIST
---

# DOT11_PHY_ID_LIST structure


## -description

> [!Important]
> [WiFiCx](/windows-hardware/drivers/netcx/wifi-wdf-class-extension-wificx) is the new Wi-Fi driver model released in Windows 11. We recommend that you use WiFiCx to take advantage of the latest features. The WDI driver model is now in maintenance mode and will only receive high priority fixes.

The DOT11_PHY_ID_LIST structure specifies a list of zero or more PHY types.

## -struct-fields

### -field Header

The type, revision, and size of the DOT11_PHY_ID_LIST structure. This member is formatted as an
     <a href="..\objectheader\ns-objectheader-ndis_object_header.md">NDIS_OBJECT_HEADER</a> structure.


The miniport driver must set the members of
     <b>Header</b> to the following values:





#### Type

This member must be set to NDIS_OBJECT_TYPE_DEFAULT.



#### Revision

This member must be set to DOT11_PHY_ID_LIST_REVISION_1.



#### Size

This member must be set to
       sizeof(DOT11_PHY_ID_LIST).

For more information about these members, see
     <a href="..\objectheader\ns-objectheader-ndis_object_header.md">NDIS_OBJECT_HEADER</a>.

### -field uNumOfEntries

The number of entries in the
     <b>dot11PhyId</b> array.

### -field uTotalNumOfEntries

The maximum number of entries that the
     <b>dot11PhyId</b> array can contain.

### -field dot11PhyId

The list of PHY identifiers (IDs).

## -syntax

```cpp
typedef struct DOT11_PHY_ID_LIST {
  NDIS_OBJECT_HEADER Header;
  ULONG              uNumOfEntries;
  ULONG              uTotalNumOfEntries;
  ULONG              dot11PhyId[1];
} DOT11_PHY_ID_LIST, *PDOT11_PHY_ID_LIST;
```

## -remarks

A PHY ID in the
    <b>dot11PhyId</b> array must be one of the following:

<ul>
<li>
An index into the table of supported PHYs that are defined by the Native 802.11 Operational
      <b>msDot11SupportedPhyTypes</b> management information base (MIB) object. For more information about PHY
      IDs and the
      <b>msDot11SupportedPhyTypes</b> MIB object, see
      <a href="/windows-hardware/drivers/network/oid-dot11-supported-phy-types">
      OID_DOT11_SUPPORTED_PHY_TYPES</a>.

</li>
<li>
A PHY ID with the value of DOT11_PHY_ID_ANY. This PHY ID is called a
      <i>wildcard PHY ID</i> and is used to specify any supported PHY on the 802.11 station. If the wildcard
      PHY ID is used, it must be the only entry in the
      <b>dot11PhyId</b> array.

</li>
</ul>
A miniport driver returns the DOT11_PHY_ID_LIST structure when queried by either
    <a href="/windows-hardware/drivers/network/oid-dot11-active-phy-list">OID_DOT11_ACTIVE_PHY_LIST</a> or
    <a href="/windows-hardware/drivers/network/oid-dot11-desired-phy-list">OID_DOT11_DESIRED_PHY_LIST</a>.

When these OIDs are queried, the miniport driver must verify that the
    <b>InformationBuffer</b> member of the
    <a href="..\ndis\nc-ndis-miniport_oid_request.md">MiniportOidRequest</a> function's
    <i>OidRequest</i> parameter is large enough to return the entire DOT11_PHY_ID_LIST structure, including
    all entries in the
    <b>dot11PhyId</b> array. The value of the
    <b>InformationBufferLength</b> member of the
    <i>OidRequest</i> parameter determines what the miniport driver must do, as the following list shows:

<ul>
<li>
If the value of the
      <b>InformationBufferLength</b> member is less than the length, in bytes, of the entire DOT11_PHY_ID_LIST
      structure, the miniport driver must do the following:

<ul>
<li>
Set the
        <b>uNumOfEntries</b> member to zero.

</li>
<li>
Set the
        <b>uTotalNumOfEntries</b> member to the number of entries in the
        <b>dot11PhyId</b> array.

</li>
<li>
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
      DOT11_PHY_ID_LIST structure, the miniport driver must do the following to complete a successful query
      request:

<ul>
<li>
For the DOT11_PHY_ID_LIST structure, set the
        <b>uNumOfEntries</b> and
        <b>uTotalNumOfEntries</b> members to the total number of entries in the
        <b>dot11PhyId</b> array.

</li>
<li>
For the
        <i>OidRequest</i> parameter, set the
        <b>BytesNeeded</b> member to zero and the
        <b>BytesWritten</b> member to the length, in bytes, of the entire DOT11_PHY_ID_LIST structure. The
        miniport driver must also copy the entire DOT11_PHY_ID_LIST structure to the
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

<a href="/windows-hardware/drivers/network/oid-dot11-active-phy-list">OID_DOT11_ACTIVE_PHY_LIST</a>



<a href="/windows-hardware/drivers/network/oid-dot11-desired-phy-list">OID_DOT11_DESIRED_PHY_LIST</a>



<a href="..\objectheader\ns-objectheader-ndis_object_header.md">NDIS_OBJECT_HEADER</a>


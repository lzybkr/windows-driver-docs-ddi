---
UID: NS:windot11.DOT11_BYTE_ARRAY
title: DOT11_BYTE_ARRAY (windot11.h)
description: The DOT11_BYTE_ARRAY structure is part of the Native 802.11 Wireless LAN interface, which is deprecated for Windows 10 and later.
old-location: netvista\dot11_byte_array.htm
tech.root: netvista
ms.date: 02/16/2018
keywords: ["DOT11_BYTE_ARRAY structure"]
ms.keywords: "*PDOT11_BYTE_ARRAY, DOT11_BYTE_ARRAY, DOT11_BYTE_ARRAY structure [Network Drivers Starting with Windows Vista], Native_802.11_data_types_b4146de4-b261-40d9-847d-1eebb48eafea.xml, PDOT11_BYTE_ARRAY, PDOT11_BYTE_ARRAY structure pointer [Network Drivers Starting with Windows Vista], netvista.dot11_byte_array, windot11/DOT11_BYTE_ARRAY, windot11/PDOT11_BYTE_ARRAY"
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
req.typenames: DOT11_BYTE_ARRAY, *PDOT11_BYTE_ARRAY
f1_keywords:
 - DOT11_BYTE_ARRAY
 - windot11/DOT11_BYTE_ARRAY
 - PDOT11_BYTE_ARRAY
 - windot11/PDOT11_BYTE_ARRAY
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - windot11.h
api_name:
 - DOT11_BYTE_ARRAY
 - PDOT11_BYTE_ARRAY
---

# DOT11_BYTE_ARRAY structure


## -description

> [!Important]
> [WiFiCx](/windows-hardware/drivers/netcx/wifi-wdf-class-extension-wificx) is the new Wi-Fi driver model released in Windows 11. We recommend that you use WiFiCx to take advantage of the latest features. The WDI driver model is now in maintenance mode and will only receive high priority fixes.

The DOT11_BYTE_ARRAY structure precedes a list of variable-length structures in the
  <b>InformationBuffer</b> member of the
  <a href="..\ndis\nc-ndis-miniport_oid_request.md">MiniportOidRequest</a> function's
  <i>OidRequest</i> parameter.

## -struct-fields

### -field Header

The type, revision, and size of the DOT11_BYTE_ARRAY structure. This member is formatted as an
     <a href="..\objectheader\ns-objectheader-ndis_object_header.md">NDIS_OBJECT_HEADER</a> structure.


The miniport driver must set the members of
     <b>Header</b> to the following values:





#### Type

This member must be set to NDIS_OBJECT_TYPE_DEFAULT.



#### Revision

This member must be set to the revision of the variable-length structures which follow the
       DOT11_BYTE_ARRAY structure. For more information about the revision of these structures, refer to the
       object identifiers (OIDS) listed in the
       "See Also" section.



#### Size

This member must be set to
       sizeof(DOT11_BYTE_ARRAY).

For more information about these members, see
     <a href="..\objectheader\ns-objectheader-ndis_object_header.md">NDIS_OBJECT_HEADER</a>.

### -field uNumOfBytes

The number of bytes in the
     <b>ucBuffer</b> array.

### -field uTotalNumOfBytes

The maximum number of bytes that the
     <b>ucBuffer</b> array requires.

### -field ucBuffer

The list of variable-length structures.

## -syntax

```cpp
typedef struct DOT11_BYTE_ARRAY {
  NDIS_OBJECT_HEADER Header;
  ULONG              uNumOfBytes;
  ULONG              uTotalNumOfBytes;
  UCHAR              ucBuffer[1];
} DOT11_BYTE_ARRAY, *PDOT11_BYTE_ARRAY;
```

## -remarks

The type of structures stored in the
    <b>ucBuffer</b> array depends on the OID set and query request. For example, when queried by
    <a href="/windows-hardware/drivers/network/oid-dot11-enum-bss-list">OID_DOT11_ENUM_BSS_LIST</a>, a miniport
    driver stores one or more DOT11_BSS_ENTRY structures in the
    <b>ucBuffer</b> array.

When queried by an OID that uses the DOT11_BYTE_ARRAY structure, the miniport driver must verify that
    the
    <b>InformationBuffer</b> member of the
    <a href="..\ndis\nc-ndis-miniport_oid_request.md">MiniportOidRequest</a> function's
    <i>OidRequest</i> parameter is large enough to return the entire structure, including all entries in the
    <b>ucBuffer</b> array. The value of the
    <b>InformationBufferLength</b> member of the
    <i>OidRequest</i> parameter determines what the miniport driver must do, as the following list shows:

<ul>
<li>
If the value of the
      <b>InformationBufferLength</b> member is less than the length, in bytes, of the entire DOT11_BYTE_ARRAY
      structure, the miniport driver must do the following:

<ul>
<li>
For the
        <i>OidRequest</i> parameter, set the
        <b>BytesWritten</b> member to zero and the
        <b>BytesNeeded</b> member to the length, in bytes, of the entire DOT11_BYTE_ARRAY structure

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
      DOT11_BYTE_ARRAY structure, the miniport driver must do the following to complete a successful query
      request:

<ul>
<li>
For the DOT11_BYTE_ARRAY structure, set the
        <b>uNumOfBytes</b> and
        <b>uTotalNumOfBytes</b> members to the total number of entries in the
        <b>ucBuffer</b> array.

</li>
<li>
For the
        <i>OidRequest</i> parameter, set the
        <b>BytesNeeded</b> member to zero and the
        <b>BytesWritten</b> member to the length, in bytes, of the entire DOT11_BYTE_ARRAY structure. The
        miniport driver must also copy the entire DOT11_BYTE_ARRAY structure to the
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

<a href="/windows-hardware/drivers/network/oid-dot11-cipher-key-mapping-key">
   OID_DOT11_CIPHER_KEY_MAPPING_KEY</a>



<a href="/windows-hardware/drivers/network/oid-dot11-enum-bss-list">OID_DOT11_ENUM_BSS_LIST</a>



<a href="..\objectheader\ns-objectheader-ndis_object_header.md">NDIS_OBJECT_HEADER</a>


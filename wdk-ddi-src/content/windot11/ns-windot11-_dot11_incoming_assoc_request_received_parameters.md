---
UID: NS:windot11._DOT11_INCOMING_ASSOC_REQUEST_RECEIVED_PARAMETERS
title: _DOT11_INCOMING_ASSOC_REQUEST_RECEIVED_PARAMETERS (windot11.h)
description: The DOT11_INCOMING_ASSOC_REQUEST_RECEIVED_PARAMETERS structure is part of the Native 802.11 Wireless LAN interface, which is deprecated for Windows 10 and later.
old-location: netvista\dot11_incoming_assoc_request_received_parameters.htm
tech.root: netvista
ms.date: 02/16/2018
keywords: ["DOT11_INCOMING_ASSOC_REQUEST_RECEIVED_PARAMETERS structure"]
ms.keywords: "*PDOT11_INCOMING_ASSOC_REQUEST_RECEIVED_PARAMETERS, DOT11_INCOMING_ASSOC_REQUEST_RECEIVED_PARAMETERS, DOT11_INCOMING_ASSOC_REQUEST_RECEIVED_PARAMETERS structure [Network Drivers Starting with Windows Vista], Native_802.11_data_types_00b02485-5af1-4945-a902-cceb1ac2e345.xml, PDOT11_INCOMING_ASSOC_REQUEST_RECEIVED_PARAMETERS, PDOT11_INCOMING_ASSOC_REQUEST_RECEIVED_PARAMETERS structure pointer [Network Drivers Starting with Windows Vista], _DOT11_INCOMING_ASSOC_REQUEST_RECEIVED_PARAMETERS, netvista.dot11_incoming_assoc_request_received_parameters, windot11/DOT11_INCOMING_ASSOC_REQUEST_RECEIVED_PARAMETERS, windot11/PDOT11_INCOMING_ASSOC_REQUEST_RECEIVED_PARAMETERS"
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
req.typenames: DOT11_INCOMING_ASSOC_REQUEST_RECEIVED_PARAMETERS, *PDOT11_INCOMING_ASSOC_REQUEST_RECEIVED_PARAMETERS
f1_keywords:
 - _DOT11_INCOMING_ASSOC_REQUEST_RECEIVED_PARAMETERS
 - windot11/_DOT11_INCOMING_ASSOC_REQUEST_RECEIVED_PARAMETERS
 - PDOT11_INCOMING_ASSOC_REQUEST_RECEIVED_PARAMETERS
 - windot11/PDOT11_INCOMING_ASSOC_REQUEST_RECEIVED_PARAMETERS
 - DOT11_INCOMING_ASSOC_REQUEST_RECEIVED_PARAMETERS
 - windot11/DOT11_INCOMING_ASSOC_REQUEST_RECEIVED_PARAMETERS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - windot11.h
api_name:
 - _DOT11_INCOMING_ASSOC_REQUEST_RECEIVED_PARAMETERS
 - PDOT11_INCOMING_ASSOC_REQUEST_RECEIVED_PARAMETERS
 - DOT11_INCOMING_ASSOC_REQUEST_RECEIVED_PARAMETERS
---

# _DOT11_INCOMING_ASSOC_REQUEST_RECEIVED_PARAMETERS structure


## -description

> [!Important]
> [WiFiCx](/windows-hardware/drivers/netcx/wifi-wdf-class-extension-wificx) is the new Wi-Fi driver model released in Windows 11. We recommend that you use WiFiCx to take advantage of the latest features. The WDI driver model is now in maintenance mode and will only receive high priority fixes.

The DOT11_INCOMING_ASSOC_REQUEST_RECEIVED_PARAMETERS structure specifies the results of the
  acceptance procedure of the 802.11 station after it receives an incoming association request, or
  re-association request, from a peer station on an infrastructure BSS.

## -struct-fields

### -field Header

The type, revision, and size of the DOT11_INCOMING_ASSOC_REQUEST_RECEIVED_PARAMETERS structure.
     This member is formatted as an
     <a href="..\objectheader\ns-objectheader-ndis_object_header.md">NDIS_OBJECT_HEADER</a> structure.


The miniport driver must set the members of
     <b>Header</b> to the following values:





#### Type

This member must be set to NDIS_OBJECT_TYPE_DEFAULT.



#### Revision

This member must be set to DOT11_INCOMING_ASSOC_REQUEST_RECEIVED_PARAMETERS_REVISION_1.



#### Size

This member must be set to
       <b>sizeof</b>(DOT11_INCOMING_ASSOC_REQUEST_RECEIVED_PARAMETERS).

For more information about these members, see
     <a href="..\objectheader\ns-objectheader-ndis_object_header.md">NDIS_OBJECT_HEADER</a>.

### -field PeerMacAddr

The media access control (MAC) address of the peer station that sent an association
     request.

### -field bReAssocReq

For nonzero values of
     <b>uStatus</b>,
     <b>bReAssocReq</b> is <b>TRUE</b> if the request from the peer station is a re-association request.

### -field uAssocReqOffset

For nonzero values of
     <b>uStatus</b>, this member specifies the offset of the request frame that is used in the association
     operation. The frame includes information elements (IEs) but does not include the 802.11 MAC
     header.

### -field uAssocReqSize

For nonzero values of
     <b>uStatus</b>, this member specifies the length, in bytes, of the request frame that is used in the
     association operation. The frame includes information elements (IEs) but does not include the 802.11 MAC
     header.

## -syntax

```cpp
typedef struct _DOT11_INCOMING_ASSOC_REQUEST_RECEIVED_PARAMETERS {
  NDIS_OBJECT_HEADER Header;
  DOT11_MAC_ADDRESS  PeerMacAddr;
  BOOLEAN            bReAssocReq;
  ULONG              uAssocReqOffset;
  ULONG              uAssocReqSize;
} DOT11_INCOMING_ASSOC_REQUEST_RECEIVED_PARAMETERS, *PDOT11_INCOMING_ASSOC_REQUEST_RECEIVED_PARAMETERS;
```

## -remarks

The Native 802.11 miniport driver includes a DOT11_INCOMING_ASSOC_REQUEST_RECEIVED_PARAMETERS
    structure when the driver makes an
    <a href="/windows-hardware/drivers/network/ndis-status-dot11-incoming-assoc-request-received">
    NDIS_STATUS_DOT11_INCOMING_ASSOC_REQUEST_RECEIVED</a> status indication.

## -see-also

<a href="/windows-hardware/drivers/network/ndis-status-dot11-incoming-assoc-request-received">
   NDIS_STATUS_DOT11_INCOMING_ASSOC_REQUEST_RECEIVED</a>



<a href="..\objectheader\ns-objectheader-ndis_object_header.md">NDIS_OBJECT_HEADER</a>


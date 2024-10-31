---
UID: NS:windot11._DOT11_RECEIVED_INVITATION_REQUEST_PARAMETERS
title: _DOT11_RECEIVED_INVITATION_REQUEST_PARAMETERS (windot11.h)
description: The parameters for a received invitation response are specified in a DOT11_RECEIVED_INVITATION_REQUEST_PARAMETERS structure. This structure is sent with an NDIS_STATUS_DOT11_WFD_RECEIVED_INVITATION_REQUEST indication.
old-location: netvista\dot11_received_invitation_request_parameters.htm
tech.root: netvista
ms.date: 02/16/2018
keywords: ["DOT11_RECEIVED_INVITATION_REQUEST_PARAMETERS structure"]
ms.keywords: "*PDOT11_RECEIVED_INVITATION_REQUEST_PARAMETERS, DOT11_RECEIVED_INVITATION_REQUEST_PARAMETERS, DOT11_RECEIVED_INVITATION_REQUEST_PARAMETERS structure [Network Drivers Starting with Windows Vista], PDOT11_RECEIVED_INVITATION_REQUEST_PARAMETERS, PDOT11_RECEIVED_INVITATION_REQUEST_PARAMETERS structure pointer [Network Drivers Starting with Windows Vista], _DOT11_RECEIVED_INVITATION_REQUEST_PARAMETERS, netvista.dot11_received_invitation_request_parameters, windot11/DOT11_RECEIVED_INVITATION_REQUEST_PARAMETERS, windot11/PDOT11_RECEIVED_INVITATION_REQUEST_PARAMETERS"
req.header: windot11.h
req.include-header: Windot11.h
req.target-type: Windows
req.target-min-winverclnt: Supported starting with   Windows 8.
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
req.typenames: DOT11_RECEIVED_INVITATION_REQUEST_PARAMETERS, *PDOT11_RECEIVED_INVITATION_REQUEST_PARAMETERS
f1_keywords:
 - _DOT11_RECEIVED_INVITATION_REQUEST_PARAMETERS
 - windot11/_DOT11_RECEIVED_INVITATION_REQUEST_PARAMETERS
 - PDOT11_RECEIVED_INVITATION_REQUEST_PARAMETERS
 - windot11/PDOT11_RECEIVED_INVITATION_REQUEST_PARAMETERS
 - DOT11_RECEIVED_INVITATION_REQUEST_PARAMETERS
 - windot11/DOT11_RECEIVED_INVITATION_REQUEST_PARAMETERS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Windot11.h
api_name:
 - _DOT11_RECEIVED_INVITATION_REQUEST_PARAMETERS
 - PDOT11_RECEIVED_INVITATION_REQUEST_PARAMETERS
 - DOT11_RECEIVED_INVITATION_REQUEST_PARAMETERS
---

# _DOT11_RECEIVED_INVITATION_REQUEST_PARAMETERS structure


## -description

> [!Important]
> [WiFiCx](/windows-hardware/drivers/netcx/wifi-wdf-class-extension-wificx) is the new Wi-Fi driver model released in Windows 11. We recommend that you use WiFiCx to take advantage of the latest features. The WDI driver model is now in maintenance mode and will only receive high priority fixes.

The parameters for a received invitation response are specified in a <b>DOT11_RECEIVED_INVITATION_REQUEST_PARAMETERS</b> structure. This structure is sent with an <a href="/windows-hardware/drivers/network/ndis-status-dot11-wfd-received-invitation-request">NDIS_STATUS_DOT11_WFD_RECEIVED_INVITATION_REQUEST</a> indication.

## -struct-fields

### -field Header

The type, revision, and size of the <b>DOT11_RECEIVED_INVITATION_REQUEST_PARAMETERS</b> structure. The required settings for the members of <b>Header</b> are the following.

<table>
<tr>
<th>Member</th>
<th>Setting</th>
</tr>
<tr>
<td><b>Type</b></td>
<td>NDIS_OBJECT_TYPE_DEFAULT</td>
</tr>
<tr>
<td><b>Revision</b></td>
<td>DOT11_RECEIVED_INVITATION_REQUEST_PARAMETERS_REVISION_1</td>
</tr>
<tr>
<td><b>Size</b></td>
<td>DOT11_SIZEOF_RECEIVED_INVITATION_REQUEST_PARAMETERS_REVISION_1</td>
</tr>
</table>

### -field TransmitterDeviceAddress

The address of the device that transmitted the invitation request packet.

### -field BSSID

The BSSID in the received invitation request packet.

### -field DialogToken

The dialog token received in the invitation request packet.

### -field RequestContext

The context data from the miniport driver. The system sends this context with the <a href="/windows-hardware/drivers/network/oid-dot11-wfd-send-invitation-response">OID_DOT11_WFD_SEND_INVITATION_RESPONSE</a> request.

### -field uIEsOffset

The offset, in bytes,  of the array of additional information elements (IEs) received in the invitation request packet. This offset is from the start of the buffer that contains this structure.

### -field uIEsLength

The length, in bytes, of the array of IEs provided at <b>uIEsOffset</b>.

## -syntax

```cpp
typedef struct _DOT11_RECEIVED_INVITATION_REQUEST_PARAMETERS {
  NDIS_OBJECT_HEADER Header;
  DOT11_MAC_ADDRESS  TransmitterDeviceAddress;
  DOT11_MAC_ADDRESS  BSSID;
  DOT11_DIALOG_TOKEN DialogToken;
  PVOID              RequestContext;
  ULONG              uIEsOffset;
  ULONG              uIEsLength;
} DOT11_RECEIVED_INVITATION_REQUEST_PARAMETERS, *PDOT11_RECEIVED_INVITATION_REQUEST_PARAMETERS;
```

## -see-also

<a href="/windows-hardware/drivers/network/oid-dot11-wfd-send-invitation-response">OID_DOT11_WFD_SEND_INVITATION_RESPONSE</a>



<a href="/windows-hardware/drivers/network/ndis-status-dot11-wfd-received-invitation-request">NDIS_STATUS_DOT11_WFD_RECEIVED_INVITATION_REQUEST</a>


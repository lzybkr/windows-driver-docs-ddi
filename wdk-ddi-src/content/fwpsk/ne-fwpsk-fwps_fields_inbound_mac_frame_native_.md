---
UID: NE:fwpsk.FWPS_FIELDS_INBOUND_MAC_FRAME_NATIVE_
title: FWPS_FIELDS_INBOUND_MAC_FRAME_NATIVE_ (fwpsk.h)
description: The FWPS_FIELDS_INBOUND_MAC_FRAME_NATIVE enumeration type specifies the data field identifiers for the FWPS_LAYER_INBOUND_MAC_FRAME_NATIVE run-time filtering layer.
old-location: netvista\fwps_fields_inbound_mac_frame_native.htm
tech.root: netvista
ms.date: 05/02/2018
keywords: ["FWPS_FIELDS_INBOUND_MAC_FRAME_NATIVE_ enumeration"]
ms.keywords: FWPS_FIELDS_INBOUND_MAC_FRAME_NATIVE, FWPS_FIELDS_INBOUND_MAC_FRAME_NATIVE enumeration [Network Drivers Starting with Windows Vista], FWPS_FIELDS_INBOUND_MAC_FRAME_NATIVE_, FWPS_FIELD_INBOUND_MAC_FRAME_NATIVE_FLAGS, FWPS_FIELD_INBOUND_MAC_FRAME_NATIVE_INTERFACE, FWPS_FIELD_INBOUND_MAC_FRAME_NATIVE_INTERFACE_INDEX, FWPS_FIELD_INBOUND_MAC_FRAME_NATIVE_INTERFACE_TYPE, FWPS_FIELD_INBOUND_MAC_FRAME_NATIVE_MAX, FWPS_FIELD_INBOUND_MAC_FRAME_NATIVE_NDIS_MEDIA_TYPE, FWPS_FIELD_INBOUND_MAC_FRAME_NATIVE_NDIS_PHYSICAL_MEDIA_TYPE, FWPS_FIELD_INBOUND_MAC_FRAME_NATIVE_NDIS_PORT, fwpsk/FWPS_FIELDS_INBOUND_MAC_FRAME_NATIVE, fwpsk/FWPS_FIELD_INBOUND_MAC_FRAME_NATIVE_FLAGS, fwpsk/FWPS_FIELD_INBOUND_MAC_FRAME_NATIVE_INTERFACE, fwpsk/FWPS_FIELD_INBOUND_MAC_FRAME_NATIVE_INTERFACE_INDEX, fwpsk/FWPS_FIELD_INBOUND_MAC_FRAME_NATIVE_INTERFACE_TYPE, fwpsk/FWPS_FIELD_INBOUND_MAC_FRAME_NATIVE_MAX, fwpsk/FWPS_FIELD_INBOUND_MAC_FRAME_NATIVE_NDIS_MEDIA_TYPE, fwpsk/FWPS_FIELD_INBOUND_MAC_FRAME_NATIVE_NDIS_PHYSICAL_MEDIA_TYPE, fwpsk/FWPS_FIELD_INBOUND_MAC_FRAME_NATIVE_NDIS_PORT, netvista.fwps_fields_inbound_mac_frame_native
req.header: fwpsk.h
req.include-header: Fwpsk.h
req.target-type: Windows
req.target-min-winverclnt: 
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
req.typenames: FWPS_FIELDS_INBOUND_MAC_FRAME_NATIVE
f1_keywords:
 - FWPS_FIELDS_INBOUND_MAC_FRAME_NATIVE_
 - fwpsk/FWPS_FIELDS_INBOUND_MAC_FRAME_NATIVE_
 - FWPS_FIELDS_INBOUND_MAC_FRAME_NATIVE
 - fwpsk/FWPS_FIELDS_INBOUND_MAC_FRAME_NATIVE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - fwpsk.h
api_name:
 - FWPS_FIELDS_INBOUND_MAC_FRAME_NATIVE_
 - FWPS_FIELDS_INBOUND_MAC_FRAME_NATIVE
---

# FWPS_FIELDS_INBOUND_MAC_FRAME_NATIVE_ enumeration


## -description

The FWPS_FIELDS_INBOUND_MAC_FRAME_NATIVE enumeration type specifies the data field identifiers for the
  FWPS_LAYER_INBOUND_MAC_FRAME_NATIVE 
  <a href="/windows/desktop/FWP/management-filtering-layer-identifiers-">run-time filtering layer</a>.

## -enum-fields

### -field FWPS_FIELD_INBOUND_MAC_FRAME_NATIVE_NDIS_MEDIA_TYPE

The inbound MAC frame native NDIS media type field.

### -field FWPS_FIELD_INBOUND_MAC_FRAME_NATIVE_NDIS_PHYSICAL_MEDIA_TYPE

The inbound MAC frame native NDIS physical media type field.

### -field FWPS_FIELD_INBOUND_MAC_FRAME_NATIVE_INTERFACE

The inbound MAC frame native interface field.

### -field FWPS_FIELD_INBOUND_MAC_FRAME_NATIVE_INTERFACE_TYPE

The inbound MAC frame native interface type field.

### -field FWPS_FIELD_INBOUND_MAC_FRAME_NATIVE_INTERFACE_INDEX

The inbound MAC frame native interface index field.

### -field FWPS_FIELD_INBOUND_MAC_FRAME_NATIVE_NDIS_PORT

The inbound MAC frame native NDIS port field.

### -field FWPS_FIELD_INBOUND_MAC_FRAME_NATIVE_L2_FLAGS

A bitwise OR of Layer 2 (L2) flags. For a list of filtering condition flags, see [Filtering Condition Flags](/windows/win32/fwp/filtering-condition-flags-).

### -field FWPS_FIELD_INBOUND_MAC_FRAME_NATIVE_COMPARTMENT_ID

The compartment that the network interface belongs to.

<div class="alert"><b>Note</b>  Supported starting with Windows 10, version 1703.</div>
<div> </div>

### -field FWPS_FIELD_INBOUND_MAC_FRAME_NATIVE_MAX

The maximum value for this enumeration. This value might change in future versions of the NDIS
     header files and binaries.



---
UID: NS:windot11._DOT11_WFD_DEVICE_CAPABILITY_CONFIG
title: _DOT11_WFD_DEVICE_CAPABILITY_CONFIG (windot11.h)
description: The device capability configuration structure sent with an OID_DOT11_WFD_DEVICE_CAPABILITY request.
old-location: netvista\_dot11_wfd_device_capability_config.htm
tech.root: netvista
ms.date: 02/16/2018
keywords: ["DOT11_WFD_DEVICE_CAPABILITY_CONFIG structure"]
ms.keywords: "*PDOT11_WFD_DEVICE_CAPABILITY_CONFIG, DOT11_WFD_DEVICE_CAPABILITY_CONFIG, DOT11_WFD_DEVICE_CAPABILITY_CONFIG structure [Network Drivers Starting with Windows Vista], PDOT11_WFD_DEVICE_CAPABILITY_CONFIG, PDOT11_WFD_DEVICE_CAPABILITY_CONFIG structure pointer [Network Drivers Starting with Windows Vista], _DOT11_WFD_DEVICE_CAPABILITY_CONFIG, netvista._dot11_wfd_device_capability_config, windot11/ DOT11_WFD_DEVICE_CAPABILITY_CONFIG, windot11/PDOT11_WFD_DEVICE_CAPABILITY_CONFIG"
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
req.typenames: DOT11_WFD_DEVICE_CAPABILITY_CONFIG, *PDOT11_WFD_DEVICE_CAPABILITY_CONFIG
f1_keywords:
 - _DOT11_WFD_DEVICE_CAPABILITY_CONFIG
 - windot11/_DOT11_WFD_DEVICE_CAPABILITY_CONFIG
 - PDOT11_WFD_DEVICE_CAPABILITY_CONFIG
 - windot11/PDOT11_WFD_DEVICE_CAPABILITY_CONFIG
 - DOT11_WFD_DEVICE_CAPABILITY_CONFIG
 - windot11/DOT11_WFD_DEVICE_CAPABILITY_CONFIG
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Windot11.h
api_name:
 - _DOT11_WFD_DEVICE_CAPABILITY_CONFIG
 - PDOT11_WFD_DEVICE_CAPABILITY_CONFIG
 - DOT11_WFD_DEVICE_CAPABILITY_CONFIG
---

# _DOT11_WFD_DEVICE_CAPABILITY_CONFIG structure


## -description

> [!Important]
> [WiFiCx](/windows-hardware/drivers/netcx/wifi-wdf-class-extension-wificx) is the new Wi-Fi driver model released in Windows 11. We recommend that you use WiFiCx to take advantage of the latest features. The WDI driver model is now in maintenance mode and will only receive high priority fixes.

The device capability configuration structure sent with an <a href="/windows-hardware/drivers/network/oid-dot11-wfd-device-capability">OID_DOT11_WFD_DEVICE_CAPABILITY</a> request.

## -struct-fields

### -field Header

Specifies the type, revision and size of the <b>DOT11_WFD_DEVICE_CAPABILITY_CONFIG</b> structure. The required settings for the members of <b>Header</b> are the following:

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
<td>DOT11_WFD_DEVICE_CAPABILITY_CONFIG_REVISION_1</td>
</tr>
<tr>
<td><b>Size</b></td>
<td>DOT11_SIZEOF_WFD_DEVICE_CAPABILITY_CONFIG_1</td>
</tr>
</table>

### -field bServiceDiscoveryEnabled

When set to TRUE, the miniport must enable Service Discovery support. The miniport must also set the Service Discovery bit in the P2P Device Capability Bitmap. If <b>bServiceDiscoveryEnabled</b> is FALSE, Service Discovery support must be disabled and the miniport must ignore all Service Discovery packets it receives.

 The system will set this to TRUE only if the miniport also sets TRUE for the <b>bServiceDiscoverySupported</b> member of <a href="..\windot11\ns-windot11-_dot11_wfd_attributes.md">DOT11_WFD_ATTRIBUTES</a>. The default value for this member is FALSE.

### -field bClientDiscoverabilityEnabled

When set to TRUE, the miniport must enable Client Discoverability support. The miniport must also set the Client Discoverability bit in the P2P Device Capability Bitmap. If <b>bClientDiscoveryEnabled</b> is FALSE,  Client Discoverability support must be disabled and the miniport must ignore all Client Discovery packets it receives.

The system will set this to TRUE only if the miniport also sets TRUE for the <b>bClientDiscoverabilitySupported</b> member of <a href="..\windot11\ns-windot11-_dot11_wfd_attributes.md">DOT11_WFD_ATTRIBUTES</a>. The default value for this member is FALSE.

### -field bConcurrentOperationSupported

When set to TRUE, the miniport must set the Concurrent Operation bit in the P2P Device Capability Bitmask. Otherwise, the Concurrent Operation bit must be cleared. The default value for this member is TRUE.

### -field bInfrastructureManagementEnabled

When set to TRUE, the miniport must enable P2P Managed Device support. The miniport must also set the P2P Infrastructure Managed bit in the P2P Device Capability Bitmap. Otherwise, the P2P Managed Device support must be disabled.

The system will set this member to TRUE only if the miniport also sets TRUE for the  <b>bInfrastructureManagementSupported</b> member of <a href="..\windot11\ns-windot11-_dot11_wfd_attributes.md">DOT11_WFD_ATTRIBUTES</a>. The default value for this member is FALSE

### -field bDeviceLimitReached

When set to TRUE, the miniport must set the Device Limit bit of the P2P Device Capability Bitmask. Otherwise, this bit must be cleared. The default value for this member is FALSE.

### -field bInvitationProcedureEnabled

When set to TRUE, the miniport must set the P2P Invitation Procedure bit of the P2P Device Capability Bitmask. Otherwise, this bit must be cleared and the miniport must ignore all Invitation request/response packets it receives. The default value for this member is TRUE.

### -field WPSVersionsEnabled

The versions of WPS enabled for the Wi-Fi Direct Device

## -syntax

```cpp
typedef struct _DOT11_WFD_DEVICE_CAPABILITY_CONFIG {
  NDIS_OBJECT_HEADER Header;
  BOOLEAN            bServiceDiscoveryEnabled;
  BOOLEAN            bClientDiscoverabilityEnabled;
  BOOLEAN            bConcurrentOperationSupported;
  BOOLEAN            bInfrastructureManagementEnabled;
  BOOLEAN            bDeviceLimitReached;
  BOOLEAN            bInvitationProcedureEnabled;
  ULONG              WPSVersionsEnabled;
} DOT11_WFD_DEVICE_CAPABILITY_CONFIG, *PDOT11_WFD_DEVICE_CAPABILITY_CONFIG;
```


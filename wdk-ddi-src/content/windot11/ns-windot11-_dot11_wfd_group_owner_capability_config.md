---
UID: NS:windot11._DOT11_WFD_GROUP_OWNER_CAPABILITY_CONFIG
title: _DOT11_WFD_GROUP_OWNER_CAPABILITY_CONFIG (windot11.h)
description: the DOT11_WFD_GROUP_OWNER_CAPABILITY_CONFIG structure is included with a OID_DOT11_WFD_GROUP_OWNER_CAPABILITY request. The structure contains capability settings for a Peer-to-Peer Group Owner (P2P GO).
old-location: netvista\_dot11_wfd_group_owner_capability_config.htm
tech.root: netvista
ms.date: 02/16/2018
keywords: ["DOT11_WFD_GROUP_OWNER_CAPABILITY_CONFIG structure"]
ms.keywords: "*PDOT11_WFD_GROUP_OWNER_CAPABILITY_CONFIG, DOT11_WFD_GROUP_OWNER_CAPABILITY_CONFIG, DOT11_WFD_GROUP_OWNER_CAPABILITY_CONFIG structure [Network Drivers Starting with Windows Vista], PDOT11_WFD_GROUP_OWNER_CAPABILITY_CONFIG, PDOT11_WFD_GROUP_OWNER_CAPABILITY_CONFIG structure pointer [Network Drivers Starting with Windows Vista], _DOT11_WFD_GROUP_OWNER_CAPABILITY_CONFIG, netvista._dot11_wfd_group_owner_capability_config, windot11/DOT11_WFD_GROUP_OWNER_CAPABILITY_CONFIG, windot11/PDOT11_WFD_GROUP_OWNER_CAPABILITY_CONFIG"
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
req.typenames: DOT11_WFD_GROUP_OWNER_CAPABILITY_CONFIG, *PDOT11_WFD_GROUP_OWNER_CAPABILITY_CONFIG
f1_keywords:
 - _DOT11_WFD_GROUP_OWNER_CAPABILITY_CONFIG
 - windot11/_DOT11_WFD_GROUP_OWNER_CAPABILITY_CONFIG
 - PDOT11_WFD_GROUP_OWNER_CAPABILITY_CONFIG
 - windot11/PDOT11_WFD_GROUP_OWNER_CAPABILITY_CONFIG
 - DOT11_WFD_GROUP_OWNER_CAPABILITY_CONFIG
 - windot11/DOT11_WFD_GROUP_OWNER_CAPABILITY_CONFIG
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Windot11.h
api_name:
 - _DOT11_WFD_GROUP_OWNER_CAPABILITY_CONFIG
 - PDOT11_WFD_GROUP_OWNER_CAPABILITY_CONFIG
 - DOT11_WFD_GROUP_OWNER_CAPABILITY_CONFIG
---

# _DOT11_WFD_GROUP_OWNER_CAPABILITY_CONFIG structure


## -description

> [!Important]
> [WiFiCx](/windows-hardware/drivers/netcx/wifi-wdf-class-extension-wificx) is the new Wi-Fi driver model released in Windows 11. We recommend that you use WiFiCx to take advantage of the latest features. The WDI driver model is now in maintenance mode and will only receive high priority fixes.

the <b>DOT11_WFD_GROUP_OWNER_CAPABILITY_CONFIG</b> structure is included with a <a href="/windows-hardware/drivers/network/oid-dot11-wfd-group-owner-capability">OID_DOT11_WFD_GROUP_OWNER_CAPABILITY</a> request. The structure contains capability settings for a Peer-to-Peer Group Owner (P2P GO).

## -struct-fields

### -field Header

Specifies the type, revision and size of the <b>DOT11_WFD_GROUP_OWNER_CAPABILITY_CONFIG</b> structure. The required settings for the members of <b>Header</b> are the following:

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
<td>DOT11_WFD_GROUP_OWNER_CAPABILITY_CONFIG_REVISION_1</td>
</tr>
<tr>
<td><b>Size</b></td>
<td>DOT11_SIZEOF_WFD_GROUP_OWNER_CAPABILITY_CONFIG_1</td>
</tr>
</table>

### -field bPersistentGroupEnabled

If TRUE, the miniport must set the Persistent P2P Group bit of the Group Capability bitmask. Otherwise, the Persistent P2P Group bit must be cleared. The default value of this member is FALSE.

### -field bIntraBSSDistributionSupported

If TRUE, the miniport must set the Intra-BSS Distribution bit of the Group Capability bitmask. Otherwise, the Intra-BSS Distribution bit must be cleared. The default value of this member is FALSE.

### -field bCrossConnectionSupported

If TRUE, the miniport must set the Cross Connection bit of the Group Capability bitmask. Otherwise, the Cross Connection bit must be cleared. The default value of this member is FALSE.

### -field bPersistentReconnectSupported

If TRUE, the miniport must set the Persistent Reconnect bit of the Group Capability bitmask. Otherwise, the Persistent Reconnect bit must be cleared. The default value of this member is FALSE.

### -field bGroupFormationEnabled

If TRUE, the miniport must set the Group Formation bit of the Group Capability bitmask. Otherwise, the Group Formation bit must be cleared. The default value of this member is FALSE.

### -field uMaximumGroupLimit

Maximum number of P2P Clients the GO should allow. Once this limit is reached, the miniport should reject the addition of any new Clients and should set the Group Limit bit in the Group Capability bitmask. The default value for this member is same as the value reported in the  <b>uGORoleClientTableSize</b> member of <a href="..\windot11\ns-windot11-_dot11_wfd_attributes.md">DOT11_WFD_ATTRIBUTES</a>.

## -syntax

```cpp
typedef struct _DOT11_WFD_GROUP_OWNER_CAPABILITY_CONFIG {
  NDIS_OBJECT_HEADER Header;
  BOOLEAN            bPersistentGroupEnabled;
  BOOLEAN            bIntraBSSDistributionSupported;
  BOOLEAN            bCrossConnectionSupported;
  BOOLEAN            bPersistentReconnectSupported;
  BOOLEAN            bGroupFormationEnabled;
  ULONG              uMaximumGroupLimit;
}  DOT11_WFD_GROUP_OWNER_CAPABILITY_CONFIG, *PDOT11_WFD_GROUP_OWNER_CAPABILITY_CONFIG;
```

## -see-also

<a href="/windows-hardware/drivers/network/oid-dot11-wfd-group-owner-capability">OID_DOT11_WFD_GROUP_OWNER_CAPABILITY</a>


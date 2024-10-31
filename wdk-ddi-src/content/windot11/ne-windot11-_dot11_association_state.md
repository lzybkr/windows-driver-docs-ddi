---
UID: NE:windot11._DOT11_ASSOCIATION_STATE
title: _DOT11_ASSOCIATION_STATE (windot11.h)
description: The DOT11_ASSOCIATION_STATE enumeration is part of the Native 802.11 Wireless LAN interface, which is deprecated for Windows 10 and later.
old-location: netvista\dot11_association_state.htm
tech.root: netvista
ms.date: 02/16/2018
keywords: ["DOT11_ASSOCIATION_STATE enumeration"]
ms.keywords: "*PDOT11_ASSOCIATION_STATE, DOT11_ASSOCIATION_STATE, DOT11_ASSOCIATION_STATE enumeration [Network Drivers Starting with Windows Vista], Native_802.11_data_types_6ec71b29-ea13-4ff5-af6c-b8f088c2671c.xml, PDOT11_ASSOCIATION_STATE, PDOT11_ASSOCIATION_STATE enumeration pointer [Network Drivers Starting with Windows Vista], _DOT11_ASSOCIATION_STATE, dot11_assoc_state_auth_assoc, dot11_assoc_state_auth_unassoc, dot11_assoc_state_unauth_unassoc, dot11_assoc_state_zero, netvista.dot11_association_state, windot11/DOT11_ASSOCIATION_STATE, windot11/PDOT11_ASSOCIATION_STATE, windot11/dot11_assoc_state_auth_assoc, windot11/dot11_assoc_state_auth_unassoc, windot11/dot11_assoc_state_unauth_unassoc, windot11/dot11_assoc_state_zero"
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
req.typenames: DOT11_ASSOCIATION_STATE, *PDOT11_ASSOCIATION_STATE
f1_keywords:
 - _DOT11_ASSOCIATION_STATE
 - windot11/_DOT11_ASSOCIATION_STATE
 - PDOT11_ASSOCIATION_STATE
 - windot11/PDOT11_ASSOCIATION_STATE
 - DOT11_ASSOCIATION_STATE
 - windot11/DOT11_ASSOCIATION_STATE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - windot11.h
api_name:
 - _DOT11_ASSOCIATION_STATE
 - PDOT11_ASSOCIATION_STATE
 - DOT11_ASSOCIATION_STATE
---

# _DOT11_ASSOCIATION_STATE enumeration


## -description

> [!Important]
> [WiFiCx](/windows-hardware/drivers/netcx/wifi-wdf-class-extension-wificx) is the new Wi-Fi driver model released in Windows 11. We recommend that you use WiFiCx to take advantage of the latest features. The WDI driver model is now in maintenance mode and will only receive high priority fixes.

The DOT11_ASSOCIATION_STATE enumeration defines the authentication and association state of an 802.11
  station.

## -enum-fields

### -field dot11_assoc_state_zero

The association state is undefined.

### -field dot11_assoc_state_unauth_unassoc

The 802.11 station is unauthenticated with the peer and is not associated.

### -field dot11_assoc_state_auth_unassoc

The 802.11 station is authenticated with the peer but is not associated.

### -field dot11_assoc_state_auth_assoc

The 802.11 station is authenticated and associated with the peer.

## -syntax

```cpp
typedef enum _DOT11_ASSOCIATION_STATE {
  dot11_assoc_state_zero            = 0,
  dot11_assoc_state_unauth_unassoc  = 1,
  dot11_assoc_state_auth_unassoc    = 2,
  dot11_assoc_state_auth_assoc      = 3
} DOT11_ASSOCIATION_STATE, *PDOT11_ASSOCIATION_STATE;
```


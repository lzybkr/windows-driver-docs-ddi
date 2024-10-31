---
UID: NE:windot11.DOT11_DIRECTION
title: DOT11_DIRECTION (windot11.h)
description: The DOT11_DIRECTION enumeration is part of the Native 802.11 Wireless LAN interface, which is deprecated for Windows 10 and later.
old-location: netvista\dot11_direction.htm
tech.root: netvista
ms.date: 02/16/2018
keywords: ["DOT11_DIRECTION enumeration"]
ms.keywords: "*PDOT11_DIRECTION, DOT11_DIRECTION, DOT11_DIRECTION enumeration [Network Drivers Starting with Windows Vista], DOT11_DIR_BOTH, DOT11_DIR_INBOUND, DOT11_DIR_OUTBOUND, Native_802.11_data_types_aef66faf-de2c-42f1-a213-ed12ea7ef583.xml, PDOT11_DIRECTION, PDOT11_DIRECTION enumeration pointer [Network Drivers Starting with Windows Vista], netvista.dot11_direction, windot11/DOT11_DIRECTION, windot11/DOT11_DIR_BOTH, windot11/DOT11_DIR_INBOUND, windot11/DOT11_DIR_OUTBOUND, windot11/PDOT11_DIRECTION"
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
req.typenames: DOT11_DIRECTION, *PDOT11_DIRECTION
f1_keywords:
 - DOT11_DIRECTION
 - windot11/DOT11_DIRECTION
 - PDOT11_DIRECTION
 - windot11/PDOT11_DIRECTION
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - windot11.h
api_name:
 - DOT11_DIRECTION
 - PDOT11_DIRECTION
---

# DOT11_DIRECTION enumeration


## -description

> [!Important]
> [WiFiCx](/windows-hardware/drivers/netcx/wifi-wdf-class-extension-wificx) is the new Wi-Fi driver model released in Windows 11. We recommend that you use WiFiCx to take advantage of the latest features. The WDI driver model is now in maintenance mode and will only receive high priority fixes.

The DOT11_DIRECTION enumeration specifies whether the 802.11 station uses a cipher key to decrypt
  received packets and/or encrypt transmitted packets.

## -enum-fields

### -field DOT11_DIR_INBOUND

The 802.11 station uses the cipher key to decrypt packets received from the access point (AP) or
     peer station.

### -field DOT11_DIR_OUTBOUND

The 802.11 station uses the cipher key to encrypt packets transmitted to the AP or peer
     station.

### -field DOT11_DIR_BOTH

The 802.11 station uses the cipher key for packets received from or transmitted to the AP or peer
     station.

## -syntax

```cpp
typedef enum DOT11_DIRECTION {
  DOT11_DIR_INBOUND   = 1,
  DOT11_DIR_OUTBOUND  = 2,
  DOT11_DIR_BOTH      = 3
} DOT11_DIRECTION, *PDOT11_DIRECTION;
```

## -see-also

<a href="..\wlanihv\nc-wlanihv-dot11ext_set_default_key.md">Dot11ExtSetDefaultKey</a>



<a href="..\windot11\ns-windot11-dot11_cipher_key_mapping_key_value.md">
   DOT11_CIPHER_KEY_MAPPING_KEY_VALUE</a>


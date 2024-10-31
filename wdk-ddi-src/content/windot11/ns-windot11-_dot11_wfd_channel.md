---
UID: NS:windot11._DOT11_WFD_CHANNEL
title: _DOT11_WFD_CHANNEL (windot11.h)
description: The DOT11_WFD_CHANNEL structure contains the channel information for a Peer-to-Pear (P2P) group.
old-location: netvista\dot11_wfd_channel.htm
tech.root: netvista
ms.date: 02/16/2018
keywords: ["DOT11_WFD_CHANNEL structure"]
ms.keywords: "*PDOT11_WFD_CHANNEL, DOT11_WFD_CHANNEL, DOT11_WFD_CHANNEL structure [Network Drivers Starting with Windows Vista], PDOT11_WFD_CHANNEL, PDOT11_WFD_CHANNEL structure pointer [Network Drivers Starting with Windows Vista], _DOT11_WFD_CHANNEL, netvista.dot11_wfd_channel, windot11/DOT11_WFD_CHANNEL, windot11/PDOT11_WFD_CHANNEL"
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
req.typenames: DOT11_WFD_CHANNEL, *PDOT11_WFD_CHANNEL
f1_keywords:
 - _DOT11_WFD_CHANNEL
 - windot11/_DOT11_WFD_CHANNEL
 - PDOT11_WFD_CHANNEL
 - windot11/PDOT11_WFD_CHANNEL
 - DOT11_WFD_CHANNEL
 - windot11/DOT11_WFD_CHANNEL
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Windot11.h
api_name:
 - _DOT11_WFD_CHANNEL
 - PDOT11_WFD_CHANNEL
 - DOT11_WFD_CHANNEL
---

# _DOT11_WFD_CHANNEL structure


## -description

> [!Important]
> [WiFiCx](/windows-hardware/drivers/netcx/wifi-wdf-class-extension-wificx) is the new Wi-Fi driver model released in Windows 11. We recommend that you use WiFiCx to take advantage of the latest features. The WDI driver model is now in maintenance mode and will only receive high priority fixes.

The <b>DOT11_WFD_CHANNEL</b> structure contains the channel information for a Peer-to-Pear (P2P) group.

## -struct-fields

### -field CountryRegionString

The country or region code where <b>OperatingClass</b> and <b>ChannelNumber</b> are valid.

### -field OperatingClass

The frequency band for <b>ChannelNumber</b>.

### -field ChannelNumber

The channel number for the P2P group.

## -syntax

```cpp
typedef struct _DOT11_WFD_CHANNEL {
  DOT11_COUNTRY_OR_REGION_STRING CountryRegionString;
  UCHAR                          OperatingClass;
  UCHAR                          ChannelNumber;
} DOT11_WFD_CHANNEL, *PDOT11_WFD_CHANNEL;
```


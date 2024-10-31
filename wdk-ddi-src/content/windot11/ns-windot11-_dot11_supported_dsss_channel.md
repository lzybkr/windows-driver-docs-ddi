---
UID: NS:windot11._DOT11_SUPPORTED_DSSS_CHANNEL
title: _DOT11_SUPPORTED_DSSS_CHANNEL (windot11.h)
description: The DOT11_SUPPORTED_DSSS_CHANNEL structure is part of the Native 802.11 Wireless LAN interface, which is deprecated for Windows 10 and later.
old-location: netvista\dot11_supported_dsss_channel.htm
tech.root: netvista
ms.date: 02/16/2018
keywords: ["DOT11_SUPPORTED_DSSS_CHANNEL structure"]
ms.keywords: "*PDOT11_SUPPORTED_DSSS_CHANNEL, DOT11_SUPPORTED_DSSS_CHANNEL, DOT11_SUPPORTED_DSSS_CHANNEL structure [Network Drivers Starting with Windows Vista], Native_802.11_data_types_2c13b1f6-0b6e-4bc7-a51f-d9c49db8d3df.xml, PDOT11_SUPPORTED_DSSS_CHANNEL, PDOT11_SUPPORTED_DSSS_CHANNEL structure pointer [Network Drivers Starting with Windows Vista], _DOT11_SUPPORTED_DSSS_CHANNEL, netvista.dot11_supported_dsss_channel, windot11/DOT11_SUPPORTED_DSSS_CHANNEL, windot11/PDOT11_SUPPORTED_DSSS_CHANNEL"
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
req.typenames: DOT11_SUPPORTED_DSSS_CHANNEL, *PDOT11_SUPPORTED_DSSS_CHANNEL
f1_keywords:
 - _DOT11_SUPPORTED_DSSS_CHANNEL
 - windot11/_DOT11_SUPPORTED_DSSS_CHANNEL
 - PDOT11_SUPPORTED_DSSS_CHANNEL
 - windot11/PDOT11_SUPPORTED_DSSS_CHANNEL
 - DOT11_SUPPORTED_DSSS_CHANNEL
 - windot11/DOT11_SUPPORTED_DSSS_CHANNEL
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - windot11.h
api_name:
 - _DOT11_SUPPORTED_DSSS_CHANNEL
 - PDOT11_SUPPORTED_DSSS_CHANNEL
 - DOT11_SUPPORTED_DSSS_CHANNEL
---

# _DOT11_SUPPORTED_DSSS_CHANNEL structure


## -description

> [!Important]
> [WiFiCx](/windows-hardware/drivers/netcx/wifi-wdf-class-extension-wificx) is the new Wi-Fi driver model released in Windows 11. We recommend that you use WiFiCx to take advantage of the latest features. The WDI driver model is now in maintenance mode and will only receive high priority fixes.

The DOT11_SUPPORTED_DSSS_CHANNEL structure specifies a supported operating frequency channel entry in
  a
  <a href="..\windot11\ns-windot11-_dot11_supported_dsss_channel_list.md">
  DOT11_SUPPORTED_DSSS_CHANNEL_LIST</a> structure.

## -struct-fields

### -field uChannel

A ULONG value, which represents a frequency channel that the 802.11 station can operate with.
     Valid channel numbers are as defined in 15.4.6.2 of
     <i>IEEE Std. 802.11-1997</i> for the following PHY types:


<ul>
<li>
Direct-sequence spread spectrum (DSSS) PHY.

</li>
<li>
High-rate DSSS (HRDSSS) PHY.

</li>
<li>
Extended-rate PHY (ERP).

</li>
<li>
High-throughput (HT) 802.11n PHY when operating in the 2.4-GHz band.

</li>
</ul>

## -syntax

```cpp
typedef struct _DOT11_SUPPORTED_DSSS_CHANNEL {
  ULONG uChannel;
} DOT11_SUPPORTED_DSSS_CHANNEL, *PDOT11_SUPPORTED_DSSS_CHANNEL;
```

## -see-also

<a href="..\windot11\ns-windot11-_dot11_supported_dsss_channel_list.md">
   DOT11_SUPPORTED_DSSS_CHANNEL_LIST</a>


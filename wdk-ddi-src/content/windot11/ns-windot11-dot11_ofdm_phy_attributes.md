---
UID: NS:windot11.DOT11_OFDM_PHY_ATTRIBUTES
title: DOT11_OFDM_PHY_ATTRIBUTES (windot11.h)
description: The DOT11_OFDM_PHY_ATTRIBUTES structure is part of the Native 802.11 Wireless LAN interface, which is deprecated for Windows 10 and later.
old-location: netvista\dot11_ofdm_phy_attributes.htm
tech.root: netvista
ms.date: 02/16/2018
keywords: ["DOT11_OFDM_PHY_ATTRIBUTES structure"]
ms.keywords: "*PDOT11_OFDM_PHY_ATTRIBUTES, DOT11_OFDM_PHY_ATTRIBUTES, DOT11_OFDM_PHY_ATTRIBUTES structure [Network Drivers Starting with Windows Vista], Native_802.11_data_types_20b6778d-4037-488b-a99f-304258498618.xml, PDOT11_OFDM_PHY_ATTRIBUTES, PDOT11_OFDM_PHY_ATTRIBUTES structure pointer [Network Drivers Starting with Windows Vista], netvista.dot11_ofdm_phy_attributes, windot11/DOT11_OFDM_PHY_ATTRIBUTES, windot11/PDOT11_OFDM_PHY_ATTRIBUTES"
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
req.typenames: DOT11_OFDM_PHY_ATTRIBUTES, *PDOT11_OFDM_PHY_ATTRIBUTES
f1_keywords:
 - DOT11_OFDM_PHY_ATTRIBUTES
 - windot11/DOT11_OFDM_PHY_ATTRIBUTES
 - PDOT11_OFDM_PHY_ATTRIBUTES
 - windot11/PDOT11_OFDM_PHY_ATTRIBUTES
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - windot11.h
api_name:
 - DOT11_OFDM_PHY_ATTRIBUTES
 - PDOT11_OFDM_PHY_ATTRIBUTES
---

# DOT11_OFDM_PHY_ATTRIBUTES structure


## -description

> [!Important]
> [WiFiCx](/windows-hardware/drivers/netcx/wifi-wdf-class-extension-wificx) is the new Wi-Fi driver model released in Windows 11. We recommend that you use WiFiCx to take advantage of the latest features. The WDI driver model is now in maintenance mode and will only receive high priority fixes.

The DOT11_OFDM_PHY_ATTRIBUTES structure defines the attributes specific to an orthogonal frequency
  division multiplexing (OFDM) PHY type.

## -struct-fields

### -field uFrequencyBandsSupported

The frequency bands in which the PHY is capable of operating. Frequency bands are defined for:


<ul>
<li>
Unlicensed national information infrastructure (U-NII) bands.

</li>
<li>
Conference of European Post and Telecommunication (CEPT) bands.

</li>
<li>
Japan 5 GHz bands.

</li>
</ul>
The frequency bands supported by the PHY are defined through the following bitmask:

<table>
<tr>
<th>Bit</th>
<th>Description</th>
</tr>
<tr>
<td>
0

</td>
<td>
Can operate in the lower (5.15-5.25 GHz) U-NII band.

</td>
</tr>
<tr>
<td>
1

</td>
<td>
Can operate in the middle (5.25-5.35 GHz) U-NII band.

</td>
</tr>
<tr>
<td>
2

</td>
<td>
Can operate in the upper (5.725-5.825 GHz) U-NII band.

</td>
</tr>
<tr>
<td>
3

</td>
<td>
Can operate in CEPT B (5.47-5.7253 GHz) band.

</td>
</tr>
<tr>
<td>
4

</td>
<td>
Can operate in the lower Japan (5.15-5 5.25 GHz) band.

</td>
</tr>
<tr>
<td>
5

</td>
<td>
Can operate in the Japan 5.0 (5.03-8 5.091 GHz) band.

</td>
</tr>
<tr>
<td>
6

</td>
<td>
Can operate in the Japan 4.9 (4.9-5.0GHz) band.

</td>
</tr>
</table>

## -syntax

```cpp
typedef struct DOT11_OFDM_PHY_ATTRIBUTES {
  ULONG uFrequencyBandsSupported;
} DOT11_OFDM_PHY_ATTRIBUTES, *PDOT11_OFDM_PHY_ATTRIBUTES;
```

## -remarks

The miniport driver defines the attributes of a PHY on the 802.11 station through the
    <a href="..\windot11\ns-windot11-dot11_phy_attributes.md">DOT11_PHY_ATTRIBUTES</a> structure, and
    formats the
    <b>OFDMAttributes</b> member as a DOT11_OFDM_PHY_ATTRIBUTES structure. The miniport driver must only do this
    if the PHY defined by the DOT11_PHY_ATTRIBUTES structure is an OFDM PHY type.

## -see-also

<a href="..\windot11\ns-windot11-dot11_phy_attributes.md">DOT11_PHY_ATTRIBUTES</a>


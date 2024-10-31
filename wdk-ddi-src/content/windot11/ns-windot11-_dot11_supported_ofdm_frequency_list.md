---
UID: NS:windot11._DOT11_SUPPORTED_OFDM_FREQUENCY_LIST
title: _DOT11_SUPPORTED_OFDM_FREQUENCY_LIST (windot11.h)
description: The DOT11_SUPPORTED_OFDM_FREQUENCY_LIST structure is part of the Native 802.11 Wireless LAN interface, which is deprecated for Windows 10 and later.
old-location: netvista\dot11_supported_ofdm_frequency_list.htm
tech.root: netvista
ms.date: 02/16/2018
keywords: ["DOT11_SUPPORTED_OFDM_FREQUENCY_LIST structure"]
ms.keywords: "*PDOT11_SUPPORTED_OFDM_FREQUENCY_LIST, DOT11_SUPPORTED_OFDM_FREQUENCY_LIST, DOT11_SUPPORTED_OFDM_FREQUENCY_LIST structure [Network Drivers Starting with Windows Vista], Native_802.11_data_types_428915da-fa98-469c-829b-5d0313a59c3b.xml, PDOT11_SUPPORTED_OFDM_FREQUENCY_LIST, PDOT11_SUPPORTED_OFDM_FREQUENCY_LIST structure pointer [Network Drivers Starting with Windows Vista], _DOT11_SUPPORTED_OFDM_FREQUENCY_LIST, netvista.dot11_supported_ofdm_frequency_list, windot11/DOT11_SUPPORTED_OFDM_FREQUENCY_LIST, windot11/PDOT11_SUPPORTED_OFDM_FREQUENCY_LIST"
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
req.typenames: DOT11_SUPPORTED_OFDM_FREQUENCY_LIST, *PDOT11_SUPPORTED_OFDM_FREQUENCY_LIST
f1_keywords:
 - _DOT11_SUPPORTED_OFDM_FREQUENCY_LIST
 - windot11/_DOT11_SUPPORTED_OFDM_FREQUENCY_LIST
 - PDOT11_SUPPORTED_OFDM_FREQUENCY_LIST
 - windot11/PDOT11_SUPPORTED_OFDM_FREQUENCY_LIST
 - DOT11_SUPPORTED_OFDM_FREQUENCY_LIST
 - windot11/DOT11_SUPPORTED_OFDM_FREQUENCY_LIST
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - windot11.h
api_name:
 - _DOT11_SUPPORTED_OFDM_FREQUENCY_LIST
 - PDOT11_SUPPORTED_OFDM_FREQUENCY_LIST
 - DOT11_SUPPORTED_OFDM_FREQUENCY_LIST
---

# _DOT11_SUPPORTED_OFDM_FREQUENCY_LIST structure


## -description

> [!Important]
> [WiFiCx](/windows-hardware/drivers/netcx/wifi-wdf-class-extension-wificx) is the new Wi-Fi driver model released in Windows 11. We recommend that you use WiFiCx to take advantage of the latest features. The WDI driver model is now in maintenance mode and will only receive high priority fixes.

The DOT11_SUPPORTED_OFDM_FREQUENCY_LIST structure specifies a list of channel center frequencies that
  the 802.11 station can operate with.

## -struct-fields

### -field uNumOfEntries

The number of entries in the
     <b>dot11SupportedOFDMFrequency</b> array.

### -field uTotalNumOfEntries

The maximum number of entries that the
     <b>dot11SupportedOFDMFrequency</b> array can contain.

### -field dot11SupportedOFDMFrequency

An array that specifies the list of supported channel center frequencies that the NIC can operate
     with. Each element in this list is formatted as a
     <a href="..\windot11\ns-windot11-_dot11_supported_ofdm_frequency.md">
     DOT11_SUPPORTED_OFDM_FREQUENCY</a> structure.

## -syntax

```cpp
typedef struct _DOT11_SUPPORTED_OFDM_FREQUENCY_LIST {
  ULONG                          uNumOfEntries;
  ULONG                          uTotalNumOfEntries;
  DOT11_SUPPORTED_OFDM_FREQUENCY dot11SupportedOFDMFrequency[1];
} DOT11_SUPPORTED_OFDM_FREQUENCY_LIST, *PDOT11_SUPPORTED_OFDM_FREQUENCY_LIST;
```

## -remarks

A miniport driver returns the DOT11_SUPPORTED_OFDM_FREQUENCY_LIST structure when queried by
    <a href="/windows-hardware/drivers/network/oid-dot11-supported-ofdm-frequency-list">
    OID_DOT11_SUPPORTED_OFDM_FREQUENCY_LIST</a>.

## -see-also

<a href="/windows-hardware/drivers/network/oid-dot11-supported-ofdm-frequency-list">
   OID_DOT11_SUPPORTED_OFDM_FREQUENCY_LIST</a>



<a href="..\windot11\ns-windot11-_dot11_supported_ofdm_frequency.md">
   DOT11_SUPPORTED_OFDM_FREQUENCY</a>


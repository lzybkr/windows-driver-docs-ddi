---
UID: NS:windot11._DOT11_RATE_SET
title: _DOT11_RATE_SET (windot11.h)
description: The DOT11_RATE_SET structure is part of the Native 802.11 Wireless LAN interface, which is deprecated for Windows 10 and later.
old-location: netvista\dot11_rate_set.htm
tech.root: netvista
ms.date: 02/16/2018
keywords: ["DOT11_RATE_SET structure"]
ms.keywords: "*PDOT11_RATE_SET, DOT11_RATE_SET, DOT11_RATE_SET structure [Network Drivers Starting with Windows Vista], Native_802.11_data_types_b2c617a6-b974-4b67-9f33-2ff5a99b55e9.xml, PDOT11_RATE_SET, PDOT11_RATE_SET structure pointer [Network Drivers Starting with Windows Vista], _DOT11_RATE_SET, netvista.dot11_rate_set, windot11/DOT11_RATE_SET, windot11/PDOT11_RATE_SET"
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
req.typenames: DOT11_RATE_SET, *PDOT11_RATE_SET
f1_keywords:
 - _DOT11_RATE_SET
 - windot11/_DOT11_RATE_SET
 - PDOT11_RATE_SET
 - windot11/PDOT11_RATE_SET
 - DOT11_RATE_SET
 - windot11/DOT11_RATE_SET
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - windot11.h
api_name:
 - _DOT11_RATE_SET
 - PDOT11_RATE_SET
 - DOT11_RATE_SET
---

# _DOT11_RATE_SET structure


## -description

> [!Important]
> [WiFiCx](/windows-hardware/drivers/netcx/wifi-wdf-class-extension-wificx) is the new Wi-Fi driver model released in Windows 11. We recommend that you use WiFiCx to take advantage of the latest features. The WDI driver model is now in maintenance mode and will only receive high priority fixes.

The DOT11_RATE_SET structure defines the set of data rates that the 802.11 station supports.

## -struct-fields

### -field uRateSetLength

The number of entries in the
     <b>ucRateSet</b> array.

### -field ucRateSet

The set of data rates.

## -syntax

```cpp
typedef struct _DOT11_RATE_SET {
  ULONG uRateSetLength;
  UCHAR ucRateSet[DOT11_RATE_SET_MAX_LENGTH];
} DOT11_RATE_SET, *PDOT11_RATE_SET;
```

## -remarks

The values that are specified in the
    <b>ucRateSet</b> array define the data rates at which the 802.11 station may transmit and receive data.
    Each value is an index into the table of data rates that are returned by the driver for a query of
    <a href="/windows-hardware/drivers/network/oid-dot11-data-rate-mapping-table">
    OID_DOT11_DATA_RATE_MAPPING_ENTRY</a>.

## -see-also

<a href="/windows-hardware/drivers/network/oid-dot11-data-rate-mapping-table">
   OID_DOT11_DATA_RATE_MAPPING_ENTRY</a>



<a href="/windows-hardware/drivers/network/oid-dot11-operational-rate-set">OID_DOT11_OPERATIONAL_RATE_SET</a>


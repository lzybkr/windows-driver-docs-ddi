---
UID: NS:windot11.DOT11_KEY_ALGO_TKIP_MIC
title: DOT11_KEY_ALGO_TKIP_MIC (windot11.h)
description: The DOT11_KEY_ALGO_TKIP_MIC structure is part of the Native 802.11 Wireless LAN interface, which is deprecated for Windows 10 and later.
old-location: netvista\dot11_key_algo_tkip_mic.htm
tech.root: netvista
ms.date: 02/16/2018
keywords: ["DOT11_KEY_ALGO_TKIP_MIC structure"]
ms.keywords: "*PDOT11_KEY_ALGO_TKIP_MIC, DOT11_KEY_ALGO_TKIP_MIC, DOT11_KEY_ALGO_TKIP_MIC structure [Network Drivers Starting with Windows Vista], Native_802.11_data_types_09def77d-63b7-4db5-8689-8be14e166738.xml, PDOT11_KEY_ALGO_TKIP_MIC, PDOT11_KEY_ALGO_TKIP_MIC structure pointer [Network Drivers Starting with Windows Vista], netvista.dot11_key_algo_tkip_mic, windot11/DOT11_KEY_ALGO_TKIP_MIC, windot11/PDOT11_KEY_ALGO_TKIP_MIC"
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
req.typenames: DOT11_KEY_ALGO_TKIP_MIC, *PDOT11_KEY_ALGO_TKIP_MIC
f1_keywords:
 - DOT11_KEY_ALGO_TKIP_MIC
 - windot11/DOT11_KEY_ALGO_TKIP_MIC
 - PDOT11_KEY_ALGO_TKIP_MIC
 - windot11/PDOT11_KEY_ALGO_TKIP_MIC
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - windot11.h
api_name:
 - DOT11_KEY_ALGO_TKIP_MIC
 - PDOT11_KEY_ALGO_TKIP_MIC
---

# DOT11_KEY_ALGO_TKIP_MIC structure


## -description

> [!Important]
> [WiFiCx](/windows-hardware/drivers/netcx/wifi-wdf-class-extension-wificx) is the new Wi-Fi driver model released in Windows 11. We recommend that you use WiFiCx to take advantage of the latest features. The WDI driver model is now in maintenance mode and will only receive high priority fixes.

The DOT11_KEY_ALGO_TKIP_MIC structure defines a cipher key that is used by the TKIP algorithm for
  data encryption and decryption. The structure also defines a message integrity code (MIC) used by the
  Michael algorithm for verifying data integrity.

## -struct-fields

### -field ucIV48Counter

The initial 48-bit value of the TKIP Sequence Counter (TSC), which is used for replay protection.
     For more information about the TSC, see
     <a href="/previous-versions/windows/hardware/network/ff565613(v=vs.85)">TKIP</a>.

### -field ulTKIPKeyLength

The length, in bytes, of the TKIP key material in the
     <b>ucTKIPMICKeys</b> array. If the authentication and cipher key derivation is performed by the operating
     system, this member will always have a value of 16.

### -field ulMICKeyLength

The length, in bytes, of the MIC key material in the
     <b>ucTKIPMICKeys</b> array. If the authentication and cipher key derivation is performed by the operating
     system, this member will always have a value of 16. The first 8 bytes will be the MIC key used for
     received packets and the last 8 bytes will be the MIC key used for transmitted packets.

### -field ucTKIPMICKeys

The TKIP and MIC key material.

## -syntax

```cpp
typedef struct DOT11_KEY_ALGO_TKIP_MIC {
  UCHAR ucIV48Counter[6];
  ULONG ulTKIPKeyLength;
  ULONG ulMICKeyLength;
  UCHAR ucTKIPMICKeys[1];
} DOT11_KEY_ALGO_TKIP_MIC, *PDOT11_KEY_ALGO_TKIP_MIC;
```

## -remarks

The TKIP key starts at
    <b>ucTKIPMICKeys</b> [0]. The MIC key starts at
    <b>ucTKIPMICKeys</b> [
    <b>ulTKIPKeyLength</b> ].

When the TKIP key is created, the 802.11 station must maintain separate TSC counters for the key for
    the send and receive path. The station must initialize the TSC counters in the following way:

<ul>
<li>
Initialize the TSC counter used for the receive path to the value specified in the
      <b>ucIV48Counter</b> member.

</li>
<li>
Initialize the TSC counter used for the send path to any value.

</li>
</ul>

## -see-also

<a href="/windows-hardware/drivers/network/oid-dot11-cipher-key-mapping-key">
   OID_DOT11_CIPHER_KEY_MAPPING_KEY</a>



<a href="/previous-versions/windows/hardware/network/ff565613(v=vs.85)">TKIP</a>



<a href="..\windot11\ns-windot11-dot11_cipher_default_key_value.md">
   DOT11_CIPHER_DEFAULT_KEY_VALUE</a>


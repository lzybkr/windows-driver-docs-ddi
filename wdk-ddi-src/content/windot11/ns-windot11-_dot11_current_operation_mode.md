---
UID: NS:windot11._DOT11_CURRENT_OPERATION_MODE
title: _DOT11_CURRENT_OPERATION_MODE (windot11.h)
description: The DOT11_CURRENT_OPERATION_MODE structure is part of the Native 802.11 Wireless LAN interface, which is deprecated for Windows 10 and later.
old-location: netvista\dot11_current_operation_mode.htm
tech.root: netvista
ms.date: 02/16/2018
keywords: ["DOT11_CURRENT_OPERATION_MODE structure"]
ms.keywords: "*PDOT11_CURRENT_OPERATION_MODE, DOT11_CURRENT_OPERATION_MODE, DOT11_CURRENT_OPERATION_MODE structure [Network Drivers Starting with Windows Vista], Native_802.11_data_types_d2f0f1a7-3e89-4ac1-acbd-a032909837a2.xml, PDOT11_CURRENT_OPERATION_MODE, PDOT11_CURRENT_OPERATION_MODE structure pointer [Network Drivers Starting with Windows Vista], _DOT11_CURRENT_OPERATION_MODE, netvista.dot11_current_operation_mode, windot11/DOT11_CURRENT_OPERATION_MODE, windot11/PDOT11_CURRENT_OPERATION_MODE"
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
req.typenames: DOT11_CURRENT_OPERATION_MODE, *PDOT11_CURRENT_OPERATION_MODE
f1_keywords:
 - _DOT11_CURRENT_OPERATION_MODE
 - windot11/_DOT11_CURRENT_OPERATION_MODE
 - PDOT11_CURRENT_OPERATION_MODE
 - windot11/PDOT11_CURRENT_OPERATION_MODE
 - DOT11_CURRENT_OPERATION_MODE
 - windot11/DOT11_CURRENT_OPERATION_MODE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - windot11.h
api_name:
 - _DOT11_CURRENT_OPERATION_MODE
 - PDOT11_CURRENT_OPERATION_MODE
 - DOT11_CURRENT_OPERATION_MODE
---

# _DOT11_CURRENT_OPERATION_MODE structure


## -description

> [!Important]
> [WiFiCx](/windows-hardware/drivers/netcx/wifi-wdf-class-extension-wificx) is the new Wi-Fi driver model released in Windows 11. We recommend that you use WiFiCx to take advantage of the latest features. The WDI driver model is now in maintenance mode and will only receive high priority fixes.

The DOT11_CURRENT_OPERATION_MODE structure defines the current Native 802.11 operation mode on the
  instance of a miniport driver that manages a wireless LAN (WLAN) adapter.

## -struct-fields

### -field uReserved

This member is reserved. The miniport driver must not modify the value of this member.

### -field uCurrentOpMode

A bitmask of the miniport driver's current operation modes. This bitmask is defined through the
      following:





#### DOT11_OPERATION_MODE_EXTENSIBLE_AP

Specifies that the miniport driver supports the Extensible Access Point (ExtAP) operation
         mode.

This value is available starting with Windows 7.



#### DOT11_OPERATION_MODE_EXTENSIBLE_STATION

Specifies that the miniport driver supports the Extensible Station (ExtSTA) operation
        mode.



#### DOT11_OPERATION_MODE_NETWORK_MONITOR

Specifies that the miniport driver supports the Network Monitor (NetMon) operation mode.



#### DOT11_OPERATION_MODE_WFD_DEVICE

Specifies that the miniport driver supports the Wi-Fi Direct Device operation mode. This mode is available starting in Windows 8.



#### DOT11_OPERATION_MODE_WFD_GROUP_OWNER

Specifies that the miniport driver supports the Wi-Fi Direct Group Owner operation mode.This mode is available starting in Windows 8.



#### DOT11_OPERATION_MODE_WFD_CLIENT

Specifies that the miniport driver supports the Wi-Fi Direct Client operation mode. This mode is available starting in Windows 8.

For more information about operation modes, see
      <a href="/windows-hardware/drivers/network/native-802-11-operation-modes">Native 802.11 Operation
      Modes</a>.

## -syntax

```cpp
typedef struct _DOT11_CURRENT_OPERATION_MODE {
  ULONG uReserved;
  ULONG uCurrentOpMode;
} DOT11_CURRENT_OPERATION_MODE, *PDOT11_CURRENT_OPERATION_MODE;
```

## -remarks

The miniport driver must specify only one operation mode in the
    <b>uCurrentOpMode</b> member.

For more information about Native 802.11 operation modes, see
    <a href="/windows-hardware/drivers/network/native-802-11-operation-modes">Native 802.11 Operation
    Modes</a>.

## -see-also

<a href="..\wlclient\ns-wlclient-_dot11_adapter.md">DOT11_ADAPTER</a>



<a href="/windows-hardware/drivers/network/native-802-11-operation-modes">Native 802.11 Operation Modes</a>



<a href="/windows-hardware/drivers/network/oid-dot11-current-operation-mode">
   OID_DOT11_CURRENT_OPERATION_MODE</a>


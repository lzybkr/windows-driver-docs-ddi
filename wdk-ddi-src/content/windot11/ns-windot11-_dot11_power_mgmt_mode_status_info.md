---
UID: NS:windot11._DOT11_POWER_MGMT_MODE_STATUS_INFO
title: _DOT11_POWER_MGMT_MODE_STATUS_INFO (windot11.h)
description: The DOT11_POWER_MGMT_MODE_STATUS_INFO structure describes the power mode of the hardware.
old-location: netvista\dot11_power_mgmt_mode_status_info.htm
tech.root: netvista
ms.date: 02/16/2018
keywords: ["DOT11_POWER_MGMT_MODE_STATUS_INFO structure"]
ms.keywords: "*PDOT11_POWER_MGMT_MODE_STATUSINFO, DOT11_POWER_MGMT_MODE_STATUS_INFO, DOT11_POWER_MGMT_MODE_STATUS_INFO structure [Network Drivers Starting with Windows Vista], PDOT11_POWER_MGMT_MODE_STATUS_INFO, PDOT11_POWER_MGMT_MODE_STATUS_INFO structure pointer [Network Drivers Starting with Windows Vista], _DOT11_POWER_MGMT_MODE_STATUS_INFO, netvista.dot11_power_mgmt_mode_status_info, windot11/DOT11_POWER_MGMT_MODE_STATUS_INFO, windot11/PDOT11_POWER_MGMT_MODE_STATUS_INFO"
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
req.typenames: DOT11_POWER_MGMT_MODE_STATUS_INFO, *PDOT11_POWER_MGMT_MODE_STATUSINFO
f1_keywords:
 - _DOT11_POWER_MGMT_MODE_STATUS_INFO
 - windot11/_DOT11_POWER_MGMT_MODE_STATUS_INFO
 - PDOT11_POWER_MGMT_MODE_STATUSINFO
 - windot11/PDOT11_POWER_MGMT_MODE_STATUSINFO
 - DOT11_POWER_MGMT_MODE_STATUS_INFO
 - windot11/DOT11_POWER_MGMT_MODE_STATUS_INFO
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Windot11.h
api_name:
 - _DOT11_POWER_MGMT_MODE_STATUS_INFO
 - PDOT11_POWER_MGMT_MODE_STATUSINFO
 - DOT11_POWER_MGMT_MODE_STATUS_INFO
---

# _DOT11_POWER_MGMT_MODE_STATUS_INFO structure


## -description

> [!Important]
> [WiFiCx](/windows-hardware/drivers/netcx/wifi-wdf-class-extension-wificx) is the new Wi-Fi driver model released in Windows 11. We recommend that you use WiFiCx to take advantage of the latest features. The WDI driver model is now in maintenance mode and will only receive high priority fixes.

The DOT11_POWER_MGMT_MODE_STATUS_INFO structure describes the power mode of the hardware.

## -struct-fields

### -field Header

The type, revision, and size of the DOT11_POWER_MGMT_MODE_STATUS_INFO structure. The required settings for the members of <b>Header</b> are the following.

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
<td>DOT11_POWER_MGMT_MODE_STATUS_INFO_REVISION_1</td>
</tr>
<tr>
<td><b>Size</b></td>
<td>DOT11_SIZEOF_POWER_MGMT_MODE_STATUS_INFO_REVISION_1</td>
</tr>
</table>

### -field PowerSaveMode

The current power mode of the hardware. The mode may be <b>dot11_power_mode_active</b> or <b>dot11_power_mode_powersave</b>, but should not be <b>dot11_power_mode_unknown</b>.

### -field uPowerSaveLevel

One of the following values describing power saving levels:

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>DOT11_POWER_SAVING_NO_POWER_SAVING</td>
<td>No power saving</td>
</tr>
<tr>
<td>DOT11_POWER_SAVING_FAST_PSP</td>
<td>Fast PSP</td>
</tr>
<tr>
<td>DOT11_POWER_SAVING_MAX_PSP</td>
<td>Maximum PSP</td>
</tr>
<tr>
<td>DOT11_POWER_SAVING_MAXIMUM_LEVEL</td>
<td>Maximum power saving level</td>
</tr>
</table>

### -field Reason

Reason that the device changed into the current power mode.

## -syntax

```cpp
typedef struct _DOT11_POWER_MGMT_MODE_STATUS_INFO {
  NDIS_OBJECT_HEADER      Header;
  DOT11_POWER_MODE        PowerSaveMode;
  ULONG                   uPowerSaveLevel;
  DOT11_POWER_MODE_REASON Reason;
} DOT11_POWER_MGMT_MODE_STATUS_INFO, *PDOT11_POWER_MGMT_MODE_STATUS_INFO;
```

## -remarks

At each transition of the mode change, a device should remember the reason it made the last change.


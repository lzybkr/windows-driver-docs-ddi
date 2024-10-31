---
UID: NE:windot11._DOT11_WPS_CONFIG_METHOD
title: _DOT11_WPS_CONFIG_METHOD (windot11.h)
description: The DOT11_WPS_CONFIG_METHOD enumeration specifies the Wi-Fi Protected Setup methods.
old-location: netvista\dot11_wps_config_method.htm
tech.root: netvista
ms.date: 02/16/2018
keywords: ["DOT11_WPS_CONFIG_METHOD enumeration"]
ms.keywords: "*PDOT11_WPS_CONFIG_METHOD, DOT11_WPS_CONFIG_METHOD, DOT11_WPS_CONFIG_METHOD enumeration [Network Drivers Starting with Windows Vista], DOT11_WPS_CONFIG_METHOD_DISPLAY, DOT11_WPS_CONFIG_METHOD_KEYPAD, DOT11_WPS_CONFIG_METHOD_NULL, DOT11_WPS_CONFIG_METHOD_PUSHBUTTON, _DOT11_WPS_CONFIG_METHOD, netvista.dot11_wps_config_method, windot11/DOT11_WPS_CONFIG_METHOD, windot11/DOT11_WPS_CONFIG_METHOD_DISPLAY, windot11/DOT11_WPS_CONFIG_METHOD_KEYPAD, windot11/DOT11_WPS_CONFIG_METHOD_NULL, windot11/DOT11_WPS_CONFIG_METHOD_PUSHBUTTON"
req.header: windot11.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Supported starting with  Windows 8.
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
req.typenames: DOT11_WPS_CONFIG_METHOD, *PDOT11_WPS_CONFIG_METHOD
f1_keywords:
 - _DOT11_WPS_CONFIG_METHOD
 - windot11/_DOT11_WPS_CONFIG_METHOD
 - PDOT11_WPS_CONFIG_METHOD
 - windot11/PDOT11_WPS_CONFIG_METHOD
 - DOT11_WPS_CONFIG_METHOD
 - windot11/DOT11_WPS_CONFIG_METHOD
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Windot11.h
api_name:
 - _DOT11_WPS_CONFIG_METHOD
 - PDOT11_WPS_CONFIG_METHOD
 - DOT11_WPS_CONFIG_METHOD
---

# _DOT11_WPS_CONFIG_METHOD enumeration


## -description

> [!Important]
> [WiFiCx](/windows-hardware/drivers/netcx/wifi-wdf-class-extension-wificx) is the new Wi-Fi driver model released in Windows 11. We recommend that you use WiFiCx to take advantage of the latest features. The WDI driver model is now in maintenance mode and will only receive high priority fixes.

The DOT11_WPS_CONFIG_METHOD enumeration specifies the Wi-Fi Protected Setup methods.

## -enum-fields

### -field DOT11_WPS_CONFIG_METHOD_NULL

No setup method is configured.

### -field DOT11_WPS_CONFIG_METHOD_DISPLAY

Setup is configured by a software user interface.

### -field DOT11_WPS_CONFIG_METHOD_NFC_TAG

### -field DOT11_WPS_CONFIG_METHOD_NFC_INTERFACE

### -field DOT11_WPS_CONFIG_METHOD_PUSHBUTTON

Setup is configured by push button enablement.

### -field DOT11_WPS_CONFIG_METHOD_KEYPAD

Setup is configured by a keypad action.

### -field DOT11_WPS_CONFIG_METHOD_WFDS_DEFAULT

## -syntax

```cpp
typedef enum _DOT11_WPS_CONFIG_METHOD {
  DOT11_WPS_CONFIG_METHOD_NULL        = 0,
  DOT11_WPS_CONFIG_METHOD_DISPLAY     = 0x0008,
  DOT11_WPS_CONFIG_METHOD_PUSHBUTTON  = 0x0080,
  DOT11_WPS_CONFIG_METHOD_KEYPAD      = 0x0100
} DOT11_WPS_CONFIG_METHOD;
```


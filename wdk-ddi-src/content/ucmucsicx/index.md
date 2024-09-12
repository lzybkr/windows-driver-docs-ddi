---
title: Ucmucsicx.h header
description: "Learn more about: Ucmucsicx.h header"
UID: NA:ucmucsicx
ms.assetid: 6839a2d9-d025-3af4-9d57-2d591f143ae1
ms.date: 01/19/2024
keywords: ["Ucmucsicx.h header"]
ms.keywords: 
ms.topic: reference
tech.root: usbref
ms.custom: RS5
f1_keywords:
 - ucmucsicx
 - ucmucsicx/ucmucsicx
api_name:
 - ucmucsicx
---

# Ucmucsicx.h header

## -description

This header is the main include header for client drivers of the UcmUcsiCx class extension. The extension provides a transport-agnostic implementation of the [UCSI specification](https://www.intel.com/content/www/us/en/products/docs/io/universal-serial-bus/bios-implementation-of-ucsi.html).

Ucmucsicx includes these headers:

- [UcmUcsiGlobals.h](../ucmucsiglobals/index.md)
- [UcmUcsiFuncEnum.h](../ucmucsifuncenum/index.md)
- [UcmUcsiDevice.h](../ucmucsidevice/index.md)
- [UcmUcsiSpec.h](../ucmucsispec/index.md)
- [UcmUcsiPpm.h](../ucmucsispec/index.md)
- [UcmUcsiPpmRequests.h](../ucmucsispec/index.md)

> [!IMPORTANT]
> Do not include the preceding headers directly. Instead, only include Ucmucsicx.h.

For more information, see:

- [Write a UcmUcsi client driver](/windows-hardware/drivers/usbcon/write-a-ucsi-driver)
- [Universal Serial Bus (USB)](/windows-hardware/drivers/usbcon/write-a-ucsi-driver)

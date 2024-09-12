---
description: "Learn more about: Ucmucsippmrequests.h header"
UID: NA:ucmucsippmrequests
title: Ucmucsippmrequests.h header
ms.assetid: 6839a2d9-d025-3af4-9d57-2d591f143ae1
ms.date: 09/30/2018
keywords: ["Ucmucsippmrequests.h header"]
ms.keywords: 
ms.topic: reference
tech.root: usbref
ms.custom: RS5
f1_keywords:
 - ucmucsippmrequests
 - ucmucsippmrequests/ucmucsippmrequests
api_name:
 - ucmucsippmrequests
---

# Ucmucsippmrequests.h header


## -description

UCM-UCSI Platform Policy Manager (PPM) abstracts the details of sending UCSI commands from Operating System Policy Manager (OPM) to PPM and receiving notifications from the PPM. It converts PPM commands to WDFREQUEST objects and forwards them to the client driver. UCSI commands are sent to the client driver as I/O control codes, declared in this header.

For information about UCSI commands, see [UCSI spec version 1.2](https://www.intel.com/content/dam/www/public/us/en/documents/technical-specifications/usb-type-c-ucsi-spec.pdf).

> Do not include this header. Instead, include Ucmucsicx.h.

For more information, see:
- [Write a UcmUcsi client driver](/windows-hardware/drivers/usbcon/write-a-ucsi-driver)
- [Universal Serial Bus (USB)](/windows-hardware/drivers/usbcon)


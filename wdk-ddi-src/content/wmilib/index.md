---
description: "Learn more about: Wmilib.h header"
UID: NA:wmilib
title: Wmilib.h header
ms.assetid: bca56998-667b-3fd4-9561-ba760c2275b6
ms.date: 05/09/2018
keywords: ["Wmilib.h header"]
ms.keywords: 
ms.topic: reference
tech.root: kernel
f1_keywords:
 - wmilib
 - wmilib/wmilib
api_name:
 - wmilib
---

# Wmilib.h header


## -description

TThis header is used in providing kernel-mode Windows Management Instrumentation (WMI) extensions to WDM. 

Drivers can use these routines in processing WMI IRPs.

- [**WmiCompleteRequest**](nf-wmilib-wmicompleterequest.md) 

- [**WmiSystemControl**](nf-wmilib-wmisystemcontrol.md) 

To handle WMI IRPs by calling WmiSystemControl, a driver must implement certain required callback routines, for information, see [Calling WmiSystemControl to Handle WMI IRPs](/windows-hardware/drivers/kernel/calling-wmisystemcontrol-to-handle-wmi-irps)


For more information, see:

- [Implementing WMI](/windows-hardware/drivers/kernel/implementing-wmi)


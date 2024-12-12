---
UID: NC:dispmprt.DXGKDDI_DISPLAYMUX_REPORT_PRESENCE
tech.root: display
title: DXGKDDI_DISPLAYMUX_REPORT_PRESENCE
ms.date: 12/12/2024
targetos: Windows
description: Learn more about the DXGKDDI_DISPLAYMUX_REPORT_PRESENCE function.
prerelease: true
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: dispmprt.h
req.idl: 
req.include-header: 
req.irql: PASSIVE_LEVEL
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: Windows 11, version 24H2, update 2025.01
req.target-min-winversvr: 
req.target-type: 
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - LibDef
api_location:
 - dispmprt.h
api_name:
 - DXGKDDI_DISPLAYMUX_REPORT_PRESENCE
f1_keywords:
 - DXGKDDI_DISPLAYMUX_REPORT_PRESENCE
 - dispmprt/DXGKDDI_DISPLAYMUX_REPORT_PRESENCE
dev_langs:
 - c++
helpviewer_keywords:
 - DXGKDDI_DISPLAYMUX_REPORT_PRESENCE
---

## -description

## -parameters

### -param DriverContext

[in] Handle to a context block that is associated with a display adapter. KMD's [**DxgkDdiAddDevice**](nc-dispmprt-dxgkddi_add_device.md) function previously provided this handle to *Dxgkrnl*.

### -param SystemHasMux

## -remarks

For more information, see [Automatic Display Switch](/windows-hardware/drivers/display/automatic-display-switch).

## -see-also


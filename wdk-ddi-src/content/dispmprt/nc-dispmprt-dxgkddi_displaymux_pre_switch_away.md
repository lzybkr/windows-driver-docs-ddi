---
UID: NC:dispmprt.DXGKDDI_DISPLAYMUX_PRE_SWITCH_AWAY
tech.root: display
title: DXGKDDI_DISPLAYMUX_PRE_SWITCH_AWAY
ms.date: 01/13/2024
targetos: Windows
description: Learn more about the DXGKDDI_DISPLAYMUX_PRE_SWITCH_AWAY function.
prerelease: false
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
 - DXGKDDI_DISPLAYMUX_PRE_SWITCH_AWAY
f1_keywords:
 - DXGKDDI_DISPLAYMUX_PRE_SWITCH_AWAY
 - dispmprt/DXGKDDI_DISPLAYMUX_PRE_SWITCH_AWAY
dev_langs:
 - c++
helpviewer_keywords:
 - DXGKDDI_DISPLAYMUX_PRE_SWITCH_AWAY
---

## -description

*Dxgkrnl* calls the kernel-mode display driver's (KMD) **DxgkddiDisplayMuxPreSwitchAway** function to notify the driver that the display currently connected to it is about to be switched away to another GPU.

## -parameters

### -param DriverContext

[in] Handle to a context block that is associated with a display adapter. KMD's [**DxgkDdiAddDevice**](nc-dispmprt-dxgkddi_add_device.md) function previously provided this handle to *Dxgkrnl*.

### -param VidPnTargetId

[in] The VidPN target that the DDI is being called for.

### -param pSwitchPrivateDataSize

[out] Pointer to a ULONG variable in which the driver writes the size in bytes of the switch private data that will be passed to the other GPU during the switch.

## -returns

**DxgkddiDisplayMuxPreSwitchAway** returns STATUS_SUCCESS if it succeeds. Otherwise, it returns an appropriate NT_STATUS error code.

## -remarks

This DDI is called under [synchronization level 2](/windows-hardware/drivers/display/threading-and-synchronization-second-level).

For more information, see [Automatic Display Switch](/windows-hardware/drivers/display/automatic-display-switch).

## -see-also

[**DxgkDdiDisplayMuxPreSwitchAwayGetPrivateData**](nc-dispmprt-dxgkddi_displaymux_pre_switch_away_get_private_data.md)

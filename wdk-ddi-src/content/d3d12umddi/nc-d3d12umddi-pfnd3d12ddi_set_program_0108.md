---
UID: NC:d3d12umddi.PFND3D12DDI_SET_PROGRAM_0108
tech.root: display
title: PFND3D12DDI_SET_PROGRAM_0108
ms.date: 05/03/2024
targetos: Windows
description: Learn more about the PFND3D12DDI_SET_PROGRAM_0108 function.
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: d3d12umddi.h
req.idl: 
req.include-header: 
req.irql: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: Windows 11, version 24H2 (WDDM 3.2)
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
 - d3d12umddi.h
api_name:
 - PFND3D12DDI_SET_PROGRAM_0108
f1_keywords:
 - PFND3D12DDI_SET_PROGRAM_0108
 - d3d12umddi/PFND3D12DDI_SET_PROGRAM_0108
dev_langs:
 - c++
helpviewer_keywords:
 - PFND3D12DDI_SET_PROGRAM_0108
---

## -description

## -parameters

UMD's **PFND3D12DDI_SET_PROGRAM_0108** function sets a program on a command list.

### -param unnamedParam1

[in] Handle to the command list in which to record the program.

### -param pDesc

[in] Pointer to a [**D3D12DDI_SET_PROGRAM_DESC_0108**](ns-d3d12umddi-d3d12ddi_set_program_desc_0108.md) structure that describes the program.

## -remarks

For more information, see [Work graphs](/windows-hardware/drivers/display/work-graphs).

## -see-also

[**D3D12DDI_SET_PROGRAM_DESC_0108**](ns-d3d12umddi-d3d12ddi_set_program_desc_0108.md)

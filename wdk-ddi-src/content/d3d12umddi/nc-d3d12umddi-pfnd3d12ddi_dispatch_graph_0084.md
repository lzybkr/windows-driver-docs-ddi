---
UID: NC:d3d12umddi.PFND3D12DDI_DISPATCH_GRAPH_0084
tech.root: display
title: PFND3D12DDI_DISPATCH_GRAPH_0084
ms.date: 09/09/2024
targetos: Windows
description: Learn more about the PFND3D12DDI_DISPATCH_GRAPH_0084 function.
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
req.target-min-winverclnt:
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
 - PFND3D12DDI_DISPATCH_GRAPH_0084
f1_keywords:
 - PFND3D12DDI_DISPATCH_GRAPH_0084
 - d3d12umddi/PFND3D12DDI_DISPATCH_GRAPH_0084
dev_langs:
 - c++
helpviewer_keywords:
 - PFND3D12DDI_DISPATCH_GRAPH_0084
---

## -description

UMD's **PFND3D12DDI_DISPATCH_GRAPH_0084** function dispatches a work graph for execution on the GPU.

## -parameters

### -param unnamedParam1

[in] Handle to the command list.

### -param unnamedParam2

[in] Pointer to a [**D3D12DDI_DISPATCH_GRAPH_DESC_0084**](ns-d3d12umddi-d3d12ddi_dispatch_graph_desc_0108.md) structure that describes the work graph.

## -remarks

For more information, see [Work graphs](/windows-hardware/drivers/display/work-graphs).

## -see-also

[**D3D12DDI_DISPATCH_GRAPH_DESC_0084**](ns-d3d12umddi-d3d12ddi_dispatch_graph_desc_0108.md)

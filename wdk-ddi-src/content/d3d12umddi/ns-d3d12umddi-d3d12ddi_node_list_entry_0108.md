---
UID: NS:d3d12umddi.D3D12DDI_NODE_LIST_ENTRY_0108
tech.root: display
title: D3D12DDI_NODE_LIST_ENTRY_0108
ms.date: 05/03/2024
targetos: Windows
description: Learn more about the D3D12DDI_NODE_LIST_ENTRY_0108 structure.
prerelease: false
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: d3d12umddi.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: Windows 11, version 24H2 (WDDM 3.2)
req.target-min-winversvr: 
req.target-type: 
req.typenames: D3D12DDI_NODE_LIST_ENTRY_0108
typedef_isUnnamed: false
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3d12umddi.h
api_name:
 - D3D12DDI_NODE_LIST_ENTRY_0108
f1_keywords:
 - D3D12DDI_NODE_LIST_ENTRY_0108
 - d3d12umddi/D3D12DDI_NODE_LIST_ENTRY_0108
dev_langs:
 - c++
helpviewer_keywords:
 - D3D12DDI_NODE_LIST_ENTRY_0108
---

## -description

The **D3D12DDI_NODE_LIST_ENTRY_0108** structure is used as part of a linked list to represent individual nodes in a work graph. Each node represents a unit of work or operation that can be executed on the GPU.

## -struct-fields

### -field pNode

Pointer to a [**D3D12DDI_NODE_0108**](ns-d3d12umddi-d3d12ddi_node_0108.md) structure that describes the node.

### -field pNext

Pointer to the next node in the list.

## -remarks

This linked list structure enables the definition of complex execution flows where each node can depend on the completion of others, forming a directed acyclic graph (DAG) of operations.

For more information, see [Work graphs](/windows-hardware/drivers/display/work-graphs).

## -see-also

[**D3D12DDI_WORK_GRAPH_DESC_0108**](ns-d3d12umddi-d3d12ddi_work_graph_desc_0108.md)

[**PFND3D12DDI_ADD_TO_STATE_OBJECT_0072**](nc-d3d12umddi-pfnd3d12ddi_add_to_state_object_0072.md)

[**PFND3D12DDI_CREATE_STATE_OBJECT_0054**](nc-d3d12umddi-pfnd3d12ddi_create_state_object_0054.md)

[**PFND3D12DDI_DISPATCH_GRAPH_0108**](nc-d3d12umddi-pfnd3d12ddi_dispatch_graph_0108.md)

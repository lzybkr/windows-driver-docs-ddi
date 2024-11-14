---
UID: NF:dbgmodel.IActionableConcept.QueryInterface
tech.root: debugger
title: IActionableConcept::QueryInterface method (dbgmodel.h)
ms.date: 11/14/2024
targetos: Windows
description: The QueryInterface method retrieves pointers to the supported interfaces on an object. This method belongs to the IActionableConcept interface.
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: dbgmodel.h
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
 - COM
api_location:
 - dbgmodel.h
api_name:
 - IActionableConcept::QueryInterface
f1_keywords:
 - IActionableConcept::QueryInterface
 - dbgmodel/IActionableConcept::QueryInterface
dev_langs:
 - c++
helpviewer_keywords:
 - QueryInterface
---

## -description

Retrieves pointers to the supported interfaces on an object. This method calls IUnknown::AddRef on the pointer it returns. 

For more information, see [IUnknown::QueryInterface](/windows/win32/api/Unknwn/nf-unknwn-iunknown-queryinterface(refiid_void)) and [Introduction to COM](/cpp/atl/introduction-to-com).

## -syntax

```cpp
HRESULT QueryInterface(
  REFIID iid,
  PVOID  *iface
);
```

## -parameters

### -param iid

The interface ID. A pointer to an existing object provided as input.

### -param iface

The returned pointer to the requested COM interface.

## -returns

This method returns HRESULT which indicates success or failure.

## -remarks

Standard COM method.

## -see-also

[IActionableConcept interface](nn-dbgmodel-iactionableconcept.md)
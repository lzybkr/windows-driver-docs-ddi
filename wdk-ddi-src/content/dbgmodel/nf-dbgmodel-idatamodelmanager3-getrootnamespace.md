---
UID: NF:dbgmodel.IDataModelManager3.GetRootNamespace
tech.root: debugger
title: IDataModelManager3::GetRootNamespace
ms.date: 11/20/2024
targetos: Windows
description: The GetRootNamespace method returns the data model's root namespace. This is an object which the data model manages and into which the debug host places certain objects.
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
 - IDataModelManager3::GetRootNamespace
f1_keywords:
 - IDataModelManager3::GetRootNamespace
 - dbgmodel/IDataModelManager3::GetRootNamespace
dev_langs:
 - c++
helpviewer_keywords:
 - GetRootNamespace
---

## -description

The GetRootNamespace method returns the data model's root namespace. This is an object which the data model manages and into which the debug host places certain objects. It is expected that at least the following hierarchy is exposed by every host: 

```cpp
• Debugger - represents the debugger which is hosting the data model

    o Sessions - a collection of sessions which represent each debug target 

         Processes -- a collection of processes which represent each process in the debug target 

            - Threads -- a collection of threads which represent each thread within a given process in the debug target
```

## -parameters

### -param rootNamespace

The root namespace of the data model is returned here.

## -returns

This method returns HRESULT that indicates success or failure.

## -remarks

## -see-also

[IDataModelManager3 interface](nn-dbgmodel-idatamodelmanager3.md)
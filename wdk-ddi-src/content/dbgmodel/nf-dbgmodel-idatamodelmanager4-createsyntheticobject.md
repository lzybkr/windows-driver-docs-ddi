---
UID: NF:dbgmodel.IDataModelManager4.CreateSyntheticObject
tech.root: debugger
title: IDataModelManager4::CreateSyntheticObject
ms.date: 12/03/2024
targetos: Windows
description: The CreateSyntheticObject method creates an empty data model object that is a dictionary of key/value/metadata tuples and concepts.
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
 - IDataModelManager4::CreateSyntheticObject
f1_keywords:
 - IDataModelManager4::CreateSyntheticObject
 - dbgmodel/IDataModelManager4::CreateSyntheticObject
dev_langs:
 - c++
helpviewer_keywords:
 - CreateSyntheticObject
---

## -description

The CreateSyntheticObject method creates an empty data model object -- a dictionary of key/value/metadata tuples and concepts. At the time of creation, there are no keys nor concepts on the object. It is a clean slate for the caller to utilize.

## -parameters

### -param context

The debug host context which will be associated with the newly created synthetic object. Not every object requires a context. If the object refers to things such as processes, threads, or memory in the address space of the host, it may need one (unless it encapsulates other objects which contain such).

### -param object

The newly created object will be returned here.

## -returns

This method returns HRESULT which indicates success or failure.

## -remarks

**Sample Code**

```cpp
ComPtr<IDataModelManager> spManager; /* get the data model manager */

ComPtr<IModelObject> spNewObject;
if (SUCCEEDED(spManager->CreateSyntheticObject(nullptr, &spNewObject)))
{
     // spNewObject is an empty object (a dictionary of key/value/metadata tuples)
}
```

## -see-also

[IDataModelManager4 interface](nn-dbgmodel-idatamodelmanager4.md)
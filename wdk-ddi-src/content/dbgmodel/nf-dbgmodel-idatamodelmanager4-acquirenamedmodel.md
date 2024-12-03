---
UID: NF:dbgmodel.IDataModelManager4.AcquireNamedModel
tech.root: debugger
title: IDataModelManager4::AcquireNamedModel
ms.date: 12/03/2024
targetos: Windows
description: The AcquireNamedModel method retrieves a data model registered under a given name.
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
 - IDataModelManager4::AcquireNamedModel
f1_keywords:
 - IDataModelManager4::AcquireNamedModel
 - dbgmodel/IDataModelManager4::AcquireNamedModel
dev_langs:
 - c++
helpviewer_keywords:
 - AcquireNamedModel
---

## -description
AcquireNamedModel looks up a well known model name and returns the data model registered by that name.  Note that if there is no model registered by the supplied name, a stub will be created and returned to the caller. 

Anything added to the stub will be added to the real object at the time a registration is made.

## -parameters

### -param modelName

The name for which to look up a registered data model.

### -param modelObject

The data model which was registered under the name given by the modelName argument will be returned here. If no such data model is registered, a stub object will be created, temporarily registered under the name given by the modelName argument and returned here. If such occurred, when the real object is registered via a call to the RegisterNamedModel method, the changes which were made to the stub object are, in effect, moved to the real data model.

## -returns

This method returns HRESULT.

## -remarks

A caller who wishes to extend a data model which is registered under a given name calls the AcquireNamedModel method in order to retrieve the object for the data model they wish to extend. This method will return whatever data model was registered via a prior call to the RegisterNamedModel method. 

As the primary purpose of the AcquireNamedModel method is to extend the model, this method has a special behavior if no model has been registered under the given name yet. If no model has been registered under the given name yet, a stub object is created, temporarily registered under the given name, and returned to the caller. When the real data model is registered via a call to the RegisterNamedModel method, any changes which were made to the stub object are, in effect, made to the real model. This removes many load order dependency issues from components which extend each other. 

**Sample Code**

```cpp
ComPtr<IDataModelManager2> spManager;    /* get the data model manager */
ComPtr<IModelObject> spExtensionModel;  /* create a data model object you want 
                                           to use as an extension (see
                                           CreateDataModelObject) */

// Get the process model so we can extend it
ComPtr<IModelObject> spProcessModel;
if (SUCCEEDED(spManager->AcquireNamedModel(L"Debugger.Models.Process", 
                                           &spProcessModel)))
{
    // We have the process model and can extend it.  Even if the name we queried 
    // for is *NOT* yet registered, we can extend what gets returned (a stub)
    // and the extensions on it will be moved to the real object 
    // once RegisterNamedModel() is called.
    if (SUCCEEDED(spProcessModel->AddParentModel(spExtensionModel.Get(), 
                                                 nullptr, 
                                                 false)))
    {
        // We have successfully extended the debugger's concept of a 
        // process with whatever we have in spExtensionModel!
    }
}
```

## -see-also

[IDataModelManager4 interface](nn-dbgmodel-idatamodelmanager4.md)
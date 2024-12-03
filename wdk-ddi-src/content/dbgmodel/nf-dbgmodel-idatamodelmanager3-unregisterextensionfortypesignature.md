---
UID: NF:dbgmodel.IDataModelManager3.UnregisterExtensionForTypeSignature
tech.root: debugger
title: IDataModelManager3::UnregisterExtensionForTypeSignature
ms.date: 11/20/2024
targetos: Windows
description: The UnregisterExtensionForTypeSignature method undoes a prior call to the RegisterExtensionForTypeSignature method.
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
 - IDataModelManager3::UnregisterExtensionForTypeSignature
f1_keywords:
 - IDataModelManager3::UnregisterExtensionForTypeSignature
 - dbgmodel/IDataModelManager3::UnregisterExtensionForTypeSignature
dev_langs:
 - c++
helpviewer_keywords:
 - UnregisterExtensionForTypeSignature
---

## -description

The UnregisterExtensionForTypeSignature method undoes a prior call to RegisterExtensionForTypeSignature. It unregisters a particular data model as an extension for either a particular type signature or as an extension for all type signatures against which the data model was registered.

## -parameters

### -param dataModel

The data model to unregister as an extension from one or more type signatures. If a specific type signature is passed in the typeSignature argument, this data model will be unregistered as an extension from that particular type signature. Newly created native/language objects with concrete types which match the signature will no longer have this data model automatically attached. If typeSignature is passed as nullptr, this data model will be unregistered from every type signature that it was registered against.

### -param typeSignature

The type signature from which dataModel should be unregistered as an extension. If this argument is nullptr, the data model given by the dataModel argument will be unregistered as an extension from every type signature it was registered against.

## -returns

This method returns HRESULT that indicates success or failure.

## -remarks

## -see-also

[IDataModelManager3 interface](nn-dbgmodel-idatamodelmanager3.md)
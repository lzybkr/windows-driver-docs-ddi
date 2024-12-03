---
UID: NF:dbgmodel.IDataModelManager3.GetModelForTypeSignature
tech.root: debugger
title: IDataModelManager3::GetModelForTypeSignature
ms.date: 11/20/2024
targetos: Windows
description: The GetModelForTypeSignature method returns the data model that was previously registered for a given type signature.
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
 - IDataModelManager3::GetModelForTypeSignature
f1_keywords:
 - IDataModelManager3::GetModelForTypeSignature
 - dbgmodel/IDataModelManager3::GetModelForTypeSignature
dev_langs:
 - c++
helpviewer_keywords:
 - GetModelForTypeSignature
---

## -description

The GetModelForTypeSignature method returns the data model that was registered against a particular type signature via a prior call to the RegisterModelForTypeSignature method. The data model returned from this method is considered the canonical visualizer for any type which matches the passed type signature. As a canonical visualizer, that data model takes over the display of the type. Display engines will, by default, hide native/language constructs of the object in favor of the view of the object presented by the data model.

## -parameters

### -param typeSignature

A type signature for which dataModel will be registered as the canonical visualizer. Any object created with a native/language type which matches the signature (and for which there is no better matching type signature) will automatically have the returned data model attached as a parent.

### -param dataModel

The data model which is registered as the canonical visualizer for all type instances which match the given type signature (and for which there is no better matching type signature.

## -returns

This method returns HRESULT that indicates success or failure.


## -remarks

## -see-also

[IDataModelManager3 interface](nn-dbgmodel-idatamodelmanager3.md)
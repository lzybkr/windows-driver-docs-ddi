---
UID: NF:dbgmodel.IDataModelManager3.CreateTypedIntrinsicObject
tech.root: debugger
title: IDataModelManager3::CreateTypedIntrinsicObject
ms.date: 11/20/2024
targetos: Windows
description: The CreateTypedIntrinsicObject method boxes intrinsic values together with a native/language type association into IModelObject.
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
 - IDataModelManager3::CreateTypedIntrinsicObject
f1_keywords:
 - IDataModelManager3::CreateTypedIntrinsicObject
 - dbgmodel/IDataModelManager3::CreateTypedIntrinsicObject
dev_langs:
 - c++
helpviewer_keywords:
 - CreateTypedIntrinsicObject
---

## -description

The CreateTypedintrinsicObject method is similar to the CreateIntrinsicObject method excepting that it allows a native/language type to be associated with the data and carried along with the boxed value. This allows the data model to represent constructs such as native enumeration types (which are simply VT_UI* or VT_I* values). Pointer types are also created with this method. A native pointer in the data model is a zero extended 64-bit quantity representing an offset into the virtual address space of the debug target. It is boxed inside a VT_UI8 and is created with this method and a type which indicates a native/language pointer.

## -parameters

### -param intrinsicData

A VARIANT containing the value which is going to be boxd inside an [IModelObject](nn-dbgmodel-imodelobject.md) container. Note that this method does not support VT_UNKNOWN constructs. Anything passed to this method must be expressable as ObjectIntrinsic

### -param type

The native/language type of the value.

### -param object

The newly boxed value (as an [IModelObject](nn-dbgmodel-imodelobject.md)) will be returned here.

## -returns

This method returns HRESULT which indicates success or failure.

## -remarks

## -see-also

[IDataModelManager3 interface](nn-dbgmodel-idatamodelmanager3.md)
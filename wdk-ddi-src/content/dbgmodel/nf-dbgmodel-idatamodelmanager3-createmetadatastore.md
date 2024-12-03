---
UID: NF:dbgmodel.IDataModelManager3.CreateMetadataStore
tech.root: debugger
title: IDataModelManager3::CreateMetadataStore
ms.date: 11/20/2024
targetos: Windows
description: The CreateMetadataStore method creates a key store that is used to hold metadata that can be associated with properties and other values.
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
 - IDataModelManager3::CreateMetadataStore
f1_keywords:
 - IDataModelManager3::CreateMetadataStore
 - dbgmodel/IDataModelManager3::CreateMetadataStore
dev_langs:
 - c++
helpviewer_keywords:
 - CreateMetadataStore
---

## -description

The CreateMetadataStore method creates a key store -- a simplified container of key/value/metadata tuples -- which is used to hold metadata that can be associated with properties and a variety of other values. 

A metadata store may have a single parent (which in turn can have a single parent). If a given metadata key is not located in a given store, its parents are checked. Most metadata stores do not have parents. It does, however, provide a way of sharing common metadata easily.

## -parameters

### -param parentStore

The parent store for the newly created metadata store. This may be null if there is no parent.

### -param metadataStore

The newly created metadata store will be returned here.

## -returns

This method returns HRESULT which indicates success or failure.

## -remarks

## -see-also

[IDataModelManager3 interface](nn-dbgmodel-idatamodelmanager3.md)
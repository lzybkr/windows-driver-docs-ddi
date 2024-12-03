---
UID: NF:dbgmodel.IDataModelManager3.Close
tech.root: debugger
title: IDataModelManager3::Close
ms.date: 11/20/2024
targetos: Windows
description: The IDataModelManager3::Close method is called on the data model manager by an application (debugger) hosting the data model in order to start the shutdown process of the data model manager.
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
 - IDataModelManager3::Close
f1_keywords:
 - IDataModelManager3::Close
 - dbgmodel/IDataModelManager3::Close
dev_langs:
 - c++
helpviewer_keywords:
 - Close
---

## -description

The Close method is called on the data model manager by an application (e.g.: debugger) hosting the data model in order to start the shutdown process of the data model manager. A host of the data model which does not the Close method prior to releasing its final reference on the data model manager may cause undefined behavior including, but not limited to, significant leaks of the management infrastructure for the data model.

## -returns

This method returns HRESULT.

## -remarks

## -see-also

[IDataModelManager3 interface](nn-dbgmodel-idatamodelmanager3.md)
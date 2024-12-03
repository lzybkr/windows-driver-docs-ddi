---
UID: NF:dbgmodel.IDataModelManager3.CreateDataModelObject
tech.root: debugger
title: IDataModelManager3::CreateDataModelObject
ms.date: 11/20/2024
targetos: Windows
description: The IDataModelManager3::createDataModelObject method is a simple helper wrapper for creating objects that are data models.
ms.keywords: ["IDataModelManager3::CreateDataModelObject"]
req.redist:
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
 - IDataModelManager3::CreateDataModelObject
f1_keywords:
 - IDataModelManager3::CreateDataModelObject
 - dbgmodel/IDataModelManager3::CreateDataModelObject
dev_langs:
 - c++
helpviewer_keywords:
 - CreateDataModelObject
---

## -description

The CreateDataModelObject method is a simple helper wrapper to create objects which are data models -- that is objects which are going to be attached as parent models to other objects. All such objects must support the data model concept via [IDataModelConcept](nn-dbgmodel-idatamodelconcept.md). This method creates a new blank synthetic object with no explicit context and adds the inpassed [IDataModelConcept](nn-dbgmodel-idatamodelconcept.md) as the newly created object's implementation of the data model concept. This can similarly be accomplished with calls to CreateSyntheticObject and SetConcept.

## -parameters

### -param dataModel

The implementation of [IDataModelConcept](nn-dbgmodel-idatamodelconcept.md) which will be automatically added to the newly created object as its implementation of the data model concept.

### -param object

The newly created synthetic object (with the data model concept set) will be returned here.

## -returns

This method returns HRESULT.

## -remarks

## -see-also

[IDataModelManager3 interface](nn-dbgmodel-idatamodelmanager3.md)
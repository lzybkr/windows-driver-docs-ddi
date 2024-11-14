---
UID: NN:dbgmodel.IConstructableConcept
tech.root: debugger
title: IConstructableConcept (dbgmodel.h)
ms.date: 11/14/2024
targetos: Windows
description: A concept that a data model can support in order to allow for construction of the object. (dbgmodel.h)
prerelease: false
req.assembly: 
req.construct-type: iface
req.ddi-compliance: 
req.header: dbgmodel.h
req.idl: 
req.include-header: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.target-type: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - COM
api_location:
 - dbgmodel.h
api_name:
 - IConstructableConcept
f1_keywords:
 - IConstructableConcept
 - dbgmodel/IConstructableConcept
dev_langs:
 - c++
helpviewer_keywords:
 - IConstructableConcept
---

## -description

A concept that a data model can support in order to allow for construction of the object.

Such a data model *MUST* support IDataModelConcept and *MUST* be registered under a name that is returned from IDataModelConcept::GetName.

## -inheritance

IConstructableConcept inherits from IUnknown.

## -methods

The **IConstructableConcept** interface has these methods.

| &nbsp; |
|-----------------|
| [IConstructableConcept::AddRef](../dbgmodel/nf-dbgmodel-iconstructableconcept-addref.md) <br><br>The AddRef method increments the reference count for an interface on an object. This method belongs to the IConstructableConcept interface. |
| [IConstructableConcept::CreateInstance](../dbgmodel/nf-dbgmodel-iconstructableconcept-createinstance.md) <br><br>The IConstructableConcept::CreateInstance method creates an instance of the object. |
| [IConstructableConcept::QueryInterface](../dbgmodel/nf-dbgmodel-iconstructableconcept-queryinterface.md) <br><br>The IConstructableConcept::QueryInterface method retrieves pointers to the supported interfaces on an object. |
| [IConstructableConcept::Release](../dbgmodel/nf-dbgmodel-iconstructableconcept-release.md) <br><br>The IConstructableConcept::Release method decrements the reference count for an interface on an object. |

## -see-also

[Debugger Data Model C++ Overview](/windows-hardware/drivers/debugger/data-model-cpp-overview)

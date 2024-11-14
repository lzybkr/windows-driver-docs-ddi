---
UID: NN:dbgmodel.IActionQueryConcept
tech.root: debugger
title: IActionQueryConcept interface (dbgmodel.h)
ms.date:  10/31/2024
targetos: Windows
description: A concept which is automatically implemented by the data model for any object which has (or can have) actions on it.  (dbgmodel.h)
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
 - IActionQueryConcept
f1_keywords:
 - IActionQueryConcept
 - dbgmodel/IActionQueryConcept
dev_langs:
 - c++
helpviewer_keywords:
 - IActionQueryConcept
---

## -description

A concept which is automatically implemented by the data model for any object which has (or can have) actions
on it. The enumerator returned from this concept will aggregate all actions implemented via metadata keys on
 methods and those implemented via direct support of IActionableConcept anywhere on the object.

Clients should *NEVER* implement this concept -- only query for it.

## -inheritance

IActionQueryConcept inherits from IUnknown.

## -methods

The **IActionQueryConcept** interface has these methods.

| &nbsp; |
|-----------------|
| [IActionQueryConcept::AddRef](../dbgmodel/nf-dbgmodel-iactionqueryconcept-addref.md) <br><br>The AddRef method increments the reference count for an interface on an object. This method belongs to the IActionQueryConcept interface. |
| [IActionQueryConcept::EnumerateActions](../dbgmodel/nf-dbgmodel-iactionqueryconcept-enumerateactions.md) <br><br>Returns an enumerator to all actions on any object implementing the IActionQueryConcept interface. |
| [IActionQueryConcept::QueryInterface](../dbgmodel/nf-dbgmodel-iactionqueryconcept-queryinterface.md) <br><br>The IActionQueryConcept::QueryInterface method retrieves pointers to the supported interfaces on an object. |
| [IActionQueryConcept::Release](../dbgmodel/nf-dbgmodel-iactionqueryconcept-release.md) <br><br>The IActionQueryConcept::Release method decrements the reference count for an interface on an object. |

## -remarks

## -see-also

[Debugger Data Model C++ Overview](/windows-hardware/drivers/debugger/data-model-cpp-overview)

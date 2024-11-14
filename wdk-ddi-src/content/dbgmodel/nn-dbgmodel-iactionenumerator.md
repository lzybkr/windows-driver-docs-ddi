---
UID: NN:dbgmodel.IActionEnumerator
tech.root: debugger
title: IActionEnumerator (dbgmodel.h)
ms.date: 11/14/2024
targetos: Windows
description:  An enumerator for actions on an object. (dbgmodel.h)
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
 - IActionEnumerator
f1_keywords:
 - IActionEnumerator
 - dbgmodel/IActionEnumerator
dev_langs:
 - c++
helpviewer_keywords:
 - IActionEnumerator
---

## -description

An enumerator for actions on an object.

## -inheritance

IActionEnumerator inherits from IUnknown.

## -methods

The **IActionEnumerator** interface has these methods.

| &nbsp; |
|-----------------|
| [IActionEnumerator::AddRef](../dbgmodel/nf-dbgmodel-iactionenumerator-addref.md) <br><br>The AddRef method increments the reference count for an interface on an object. This method belongs to the IActionEnumerator interface. |
| [IActionEnumerator::GetNext](../dbgmodel/nf-dbgmodel-iactionenumerator-getnext.md) <br><br> The IActionEnumerator::GetNext method gets the next action on the object. |
| [IActionEnumerator::QueryInterface](../dbgmodel/nf-dbgmodel-iactionenumerator-queryinterface.md) <br><br>The IActionEnumerator::QueryInterface method retrieves pointers to the supported interfaces on an object. |
| [IActionEnumerator::Release](../dbgmodel/nf-dbgmodel-iactionenumerator-release.md) <br><br>The IActionEnumerator::Release method decrements the reference count for an interface on an object. |
| [IActionEnumerator::Reset](../dbgmodel/nf-dbgmodel-iactionenumerator-reset.md) <br><br>The IActionEnumerator::Reset method resets the enumerator to the first action.  |

## -remarks

## -see-also

[Debugger Data Model C++ Overview](/windows-hardware/drivers/debugger/data-model-cpp-overview)

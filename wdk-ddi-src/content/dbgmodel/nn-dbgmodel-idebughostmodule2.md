---
UID: NN:dbgmodel.IDebugHostModule2
title: IDebugHostModule2 (dbgmodel.h)
description: The IDebugHostModule2 (dbgmodel.h) interface is an IDebugHostSymbol derived interface that provides access to a particular module.
ms.date: 06/11/2019
keywords: ["IDebugHostModule2 interface"]
req.header: dbgmodel.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
targetos: Windows
tech.root: debugger
ms.custom: RS5
f1_keywords:
 - IDebugHostModule2
 - dbgmodel/IDebugHostModule2
topic_type:
 - apiref
api_type:
 - COM
api_location:
 - dbgmodel.h
api_name:
 - IDebugHostModule2
---

# IDebugHostModule2 interface

## -description

An ([IDebugHostSymbol](nn-dbgmodel-idebughostsymbol.md) derived) interface to a particular module.

This version 2 of the interface supports all of the previous methods with identical signatures and includes additional new methods that provide added functionality. The new methods are listed in the header at the end of the section for that interface.

## -inheritance

IDebugHostModule2 inherits from [IDebugHostModule](nn-dbgmodel-idebughostmodule.md).

## -remarks

The debugger's notion of a module that is loaded within some address space is represented in two distinct ways in the data model: 

- At the type system level via the [IDebugHostModule](nn-dbgmodel-idebughostmodule.md) interface. Here, a module is a symbol and core attributes of the module are interface method calls

- Projected at the data model level via the Debugger.Models.Module data model. This is an extensible encapsulation of the type system [IDebugHostModule](nn-dbgmodel-idebughostmodule.md) representation of a module.

## -see-also

[Debugger Data Model C++ Overview](/windows-hardware/drivers/debugger/data-model-cpp-overview)

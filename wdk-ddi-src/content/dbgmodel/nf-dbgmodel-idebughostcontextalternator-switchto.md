---
UID: NF:dbgmodel.IDebugHostContextAlternator.SwitchTo
tech.root: debugger
title: IDebugHostContextAlternator::SwitchTo
ms.date: 12/16/2024
targetos: Windows
description: The SwitchTo method changes or switches the debugger engine context to the IDebugHostContext from which the IDebugHostContextControl was retrieved.
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
 - IDebugHostContextAlternator::SwitchTo
f1_keywords:
 - IDebugHostContextAlternator::SwitchTo
 - dbgmodel/IDebugHostContextAlternator::SwitchTo
dev_langs:
 - c++
helpviewer_keywords:
 - SwitchTo
---

## -description

The SwitchTo method changes or switches the debugger engine context to the IDebugHostContext from which the IDebugHostContextControl was retrieved. Unlike a full context switch, this change is temporary, and not all debugger functionalities may be available or may work as expected unless the context is switched back.

## -parameters

### -param fullSwitch

A boolean value that indicates whether the switch should be a "full" context switch. If set to true, it indicates a complete switch to the new context, while false indicates a temporary switch.

## -returns

## -remarks

It allows for transitioning between different debugging contexts without committing to a permanent switch. This feature is useful in scenarios where developers want to test or inspect a particular context without losing the original debugging state.

When using this method, it is important to note that, during a temporary switch, not all functionalities of the debugger may be functional or reliable. If the developer requires full access to all debugging capabilities, it is recommended to perform a full switch instead by passing true for the fullSwitch parameter.

## -see-also

- [IDebugHostContextAlternator interface](nn-dbgmodel-idebughostcontextalternator.md)
- [IDebugHostContextControl interface](nn-dbgmodel-idebughostcontextcontrol.md)
- [IDebugHostContext interface](nn-dbgmodel-idebughostcontext.md)
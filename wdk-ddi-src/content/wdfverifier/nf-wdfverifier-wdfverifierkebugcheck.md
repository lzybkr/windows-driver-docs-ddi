---
UID: NF:wdfverifier.WdfVerifierKeBugCheck
title: WdfVerifierKeBugCheck function (wdfverifier.h)
description: The WdfVerifierKeBugCheck function creates a bug check.
old-location: wdf\wdfverifierkebugcheck.htm
tech.root: wdf
ms.date: 02/26/2018
keywords: ["WdfVerifierKeBugCheck function"]
ms.keywords: DFDebugRef_05774709-97ed-4fcc-b0b2-9fdac9a34094.xml, WdfVerifierKeBugCheck, WdfVerifierKeBugCheck function, kmdf.wdfverifierkebugcheck, wdf.wdfverifierkebugcheck, wdfverifier/WdfVerifierKeBugCheck
req.header: wdfverifier.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.ddi-compliance: DriverCreate
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (KMDF); WUDFx02000.dll (UMDF)
req.dll: 
req.irql: Any level
targetos: Windows
req.typenames: 
f1_keywords:
 - WdfVerifierKeBugCheck
 - wdfverifier/WdfVerifierKeBugCheck
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Wdf01000.sys
 - Wdf01000.sys.dll
 - WUDFx02000.dll
 - WUDFx02000.dll.dll
api_name:
 - WdfVerifierKeBugCheck
---

# WdfVerifierKeBugCheck function


## -description

<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WdfVerifierKeBugCheck</b> function creates a bug check.

## -parameters

### -param BugCheckCode [in]


One of the <a href="/windows-hardware/drivers/debugger/bug-check-code-reference2">bug check codes</a> that are defined in <i>Bugcodes.h</i>.

### -param BugCheckParameter1 [in]


For information about this parameter, see the specified bug check code's description.

### -param BugCheckParameter2 [in]


For information about this parameter, see the specified bug check code's description.

### -param BugCheckParameter3 [in]


For information about this parameter, see the specified bug check code's description.

### -param BugCheckParameter4 [in]


For information about this parameter, see the specified bug check code's description.

## -remarks

If your Kernel-Mode Driver Framework (KMDF) driver calls <b>WdfVerifierKeBugCheck</b>, the operating system halts and displays a <a href="/windows-hardware/drivers/debugger/blue-screen-data">blue screen</a> unless a debugger is running. For more information, see  [Getting Started with WinDbg - Kernel Mode](/windows-hardware/drivers/debugger/getting-started-with-windbg--kernel-mode-).

If your  User-Mode Driver Framework (UMDF) driver (version 2.0 or later) calls <b>WdfVerifierKeBugCheck</b>, the framework does not use  the parameters that the driver supplies.   In this case, the framework breaks into the debugger if one is connected. If a debugger is not connected, the framework generates an exception, and the default UMDF exception handler creates a minidump file. For more information about unhandled exceptions in the driver host process, see <a href="/windows-hardware/drivers/wdf/how-umdf-reports-errors">How UMDF Reports Errors</a>.

For more information about debugging your driver, see <a href="/windows-hardware/drivers/wdf/debugging-a-wdf-driver">Debugging WDF Drivers</a>.


#### Examples

The following code example creates a bug check that uses the <a href="/windows-hardware/drivers/debugger/bug-check-0x44--multiple-irp-complete-requests">MULTIPLE_IRP_COMPLETE_REQUESTS</a> bug check code.

```cpp
WdfVerifierKeBugCheck(
                      MULTIPLE_IRP_COMPLETE_REQUESTS,
                      (ULONG_PTR) irp,
                      (ULONG_PTR) srb,
                      0,
                      0
                      );
```

## -see-also

<a href="/windows-hardware/drivers/ddi/wdfverifier/nf-wdfverifier-wdfverifierdbgbreakpoint">WdfVerifierDbgBreakPoint</a>

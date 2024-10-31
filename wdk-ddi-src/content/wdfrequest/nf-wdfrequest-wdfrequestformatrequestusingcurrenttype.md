---
UID: NF:wdfrequest.WdfRequestFormatRequestUsingCurrentType
title: WdfRequestFormatRequestUsingCurrentType function (wdfrequest.h)
description: The WdfRequestFormatRequestUsingCurrentType method formats a specified I/O request so that the driver can forward it, unmodified, to the driver's local I/O target.
old-location: wdf\wdfrequestformatrequestusingcurrenttype.htm
tech.root: wdf
ms.date: 10/01/2024
keywords: ["WdfRequestFormatRequestUsingCurrentType function"]
ms.keywords: DFRequestObjectRef_c84fc560-9492-448a-9886-754c2857eba5.xml, WdfRequestFormatRequestUsingCurrentType, WdfRequestFormatRequestUsingCurrentType method, kmdf.wdfrequestformatrequestusingcurrenttype, wdf.wdfrequestformatrequestusingcurrenttype, wdfrequest/WdfRequestFormatRequestUsingCurrentType
req.header: wdfrequest.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.ddi-compliance: DriverCreate, InvalidReqAccess, InvalidReqAccessLocal, KmdfIrql, KmdfIrql2, RequestFormattedValid
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (KMDF); WUDFx02000.dll (UMDF)
req.dll: 
req.irql: <=DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - WdfRequestFormatRequestUsingCurrentType
 - wdfrequest/WdfRequestFormatRequestUsingCurrentType
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
 - WdfRequestFormatRequestUsingCurrentType
---

# WdfRequestFormatRequestUsingCurrentType function


## -description

<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WdfRequestFormatRequestUsingCurrentType</b> method formats a specified I/O request so that the driver can <a href="/windows-hardware/drivers/wdf/forwarding-i-o-requests">forward</a> it, unmodified, to the driver's local I/O target.

## -parameters

### -param Request [in]


A handle to a framework request object that the driver received from one of its I/O queues.

## -remarks

A bug check occurs if the driver supplies an invalid object handle.



When your driver <a href="/windows-hardware/drivers/wdf/receiving-i-o-requests">receives an I/O request</a>, sometimes you will want the driver to forward the request, unmodified, to its local I/O target. To forward such a request, the driver must:

<ol>
<li>
Call <b>WdfRequestFormatRequestUsingCurrentType</b> to format the request object so that the framework can pass the request to the driver's local I/O target.

</li>
<li>
Call <a href="/windows-hardware/drivers/ddi/wdfrequest/nf-wdfrequest-wdfrequestsend">WdfRequestSend</a> to send the request to the I/O target.

</li>
</ol>
For more information about <b>WdfRequestFormatRequestUsingCurrentType</b>, see <a href="/windows-hardware/drivers/wdf/forwarding-i-o-requests">Forwarding I/O Requests</a>.


#### Examples

The following code example is an <a href="/windows-hardware/drivers/ddi/wdfio/nc-wdfio-evt_wdf_io_queue_io_default">EvtIoDefault</a> callback function that forwards every I/O request that it receives, without modification, to the device's local I/O target.

```cpp
VOID
MyEvtIoDefault(
    WDFQUEUE Queue,
    WDFREQUEST Request
    )
{
    WDF_REQUEST_SEND_OPTIONS options;
    NTSTATUS status;

    WdfRequestFormatRequestUsingCurrentType(Request);

    WDF_REQUEST_SEND_OPTIONS_INIT(
                                  &options,
                                  WDF_REQUEST_SEND_OPTION_SEND_AND_FORGET
                                  );

    ret = WdfRequestSend (
                          Request,
                          WdfDeviceGetIoTarget(WdfIoQueueGetDevice(Queue)),
                          &options
                          );
    if (!ret) {
        status = WdfRequestGetStatus(Request);
        WdfRequestComplete(
                           Request,
                           status
                           );
    }
    return;
}
```

## -see-also

<a href="/windows-hardware/drivers/ddi/wdfrequest/nf-wdfrequest-wdfrequestsend">WdfRequestSend</a>



<a href="/windows-hardware/drivers/ddi/wdfrequest/nf-wdfrequest-wdfrequestwdmformatusingstacklocation">WdfRequestWdmFormatUsingStackLocation</a>

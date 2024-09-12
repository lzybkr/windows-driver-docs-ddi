---
UID: NF:wdfdevice.WdfDeviceMapIoSpace
title: WdfDeviceMapIoSpace function (wdfdevice.h)
description: The WdfDeviceMapIoSpace function maps the given physical address range to system address space and returns a pseudo base address.
old-location: wdf\wdfdevicemapiospace.htm
tech.root: wdf
ms.date: 08/20/2024
keywords: ["WdfDeviceMapIoSpace function"]
ms.keywords: WdfDeviceMapIoSpace, WdfDeviceMapIoSpace function, wdf.wdfdevicemapiospace, wdfdevice/WdfDeviceMapIoSpace
req.header: wdfdevice.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: Windows 8.1
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 2.0
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: WUDFx02000.lib
req.dll: WUDFx02000.dll
req.irql: PASSIVE_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - WdfDeviceMapIoSpace
 - wdfdevice/WdfDeviceMapIoSpace
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - WUDFx02000.dll
api_name:
 - WdfDeviceMapIoSpace
---

# WdfDeviceMapIoSpace function


## -description

<p class="CCE_Message">[Applies to UMDF only]</p>

The <b>WdfDeviceMapIoSpace</b> function maps the given physical address range to system address space and returns a pseudo base address.

## -parameters

### -param Device [in]


A handle to a framework device object.

### -param PhysicalAddress [in]


Specifies the starting 64-bit physical address of the I/O range to be mapped.

### -param NumberOfBytes [in]


Specifies a value greater than zero, indicating the number of bytes to be mapped.

### -param CacheType [in]


Specifies a <a href="/windows-hardware/drivers/ddi/wdm/ne-wdm-_memory_caching_type">MEMORY_CACHING_TYPE</a> value, which indicates the cache attribute to use to map the physical address range. The MEMORY_CACHING_TYPE enumeration type is defined in Wdfdevice.h.

### -param PseudoBaseAddress [out]


The address of a location that receives a pointer to the pseudo base address.

## -returns

If the operation succeeds, the function returns STATUS_SUCCESS. 

The function might return other <a href="/windows-hardware/drivers/kernel/ntstatus-values">NTSTATUS values</a>.

## -remarks

This function is the UMDF version 2 equivalent of <a href="/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfdevice3-mapiospace">IWDFDevice3::MapIoSpace</a>.

A driver must call this function during device start-up if it receives translated resources of type <b>CmResourceTypeMemory</b> in a <a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_cm_partial_resource_descriptor">CM_PARTIAL_RESOURCE_DESCRIPTOR</a> structure. <b>WdfDeviceMapIoSpace</b> maps the physical address returned in the resource list to a framework-managed address referred to as the pseudo base address. 

 The driver can then use the pseudo base address to access device registers with WDF_READ_REGISTER_<i>Xxx</i> and WDF_WRITE_REGISTER_<i>Xxx</i> functions. 

A driver that calls <b>WdfDeviceMapIoSpace</b> must set the <b>UmdfDirectHardwareAccess</b> INF directive to <b>AllowDirectHardwareAccess</b>.

 If the driver sets the <b>UmdfRegisterAccessMode</b> INF directive to <b>RegisterAccessUsingUserModeMapping</b>, calling <b>WdfDeviceMapIoSpace</b> also maps the given physical address range to a user-mode base address range that the driver can subsequently access by calling <a href="/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdevicegethardwareregistermappedaddress">WdfDeviceGetHardwareRegisterMappedAddress</a>.

 For more information about  INF directives that UMDF drivers can use, see <a href="/windows-hardware/drivers/wdf/specifying-wdf-directives-in-inf-files">Specifying WDF Directives in INF Files</a>.

For more information about parsing hardware resources starting in UMDF version 2, see <a href="/windows-hardware/drivers/wdf/finding-and-mapping-hardware-resources">Handling Hardware Resources in a UMDF Driver</a>.

The PHYSICAL_ADDRESS type is defined in Wudfwdm.h, as follows:<pre class="syntax"><code>typedef LARGE_INTEGER PHYSICAL_ADDRESS;</code></pre>


For an example that shows how a driver finds and maps memory-mapped register resources, see <a href="/windows-hardware/drivers/wdf/reading-and-writing-to-device-registers">Reading and Writing to Device Registers</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/wudfddi/nf-wudfddi-iwdfdevice3-mapiospace">IWDFDevice3::MapIoSpace</a>



<a href="/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdeviceunmapiospace">WdfDeviceUnmapIoSpace</a>

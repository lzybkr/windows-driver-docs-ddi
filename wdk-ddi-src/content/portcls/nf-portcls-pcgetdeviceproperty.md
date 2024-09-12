---
UID: NF:portcls.PcGetDeviceProperty
title: PcGetDeviceProperty function (portcls.h)
description: The PcGetDeviceProperty function returns the requested device property from the registry.
old-location: audio\pcgetdeviceproperty.htm
tech.root: audio
ms.date: 05/08/2018
keywords: ["PcGetDeviceProperty function"]
ms.keywords: PcGetDeviceProperty, PcGetDeviceProperty function [Audio Devices], audio.pcgetdeviceproperty, audpc-routines_c95326e5-dc8f-4a04-b31d-6c4e79cc6771.xml, portcls/PcGetDeviceProperty
req.header: portcls.h
req.include-header: Portcls.h
req.target-type: Universal
req.target-min-winverclnt: The PortCls system driver implements the PcGetDeviceProperty function in Microsoft Windows 98/Me and in Windows 2000 and later operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Portcls.lib
req.dll: 
req.irql: PASSIVE_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - PcGetDeviceProperty
 - portcls/PcGetDeviceProperty
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Portcls.lib
 - Portcls.dll
api_name:
 - PcGetDeviceProperty
---

# PcGetDeviceProperty function


## -description

The <b>PcGetDeviceProperty</b> function returns the requested device property from the registry.

## -parameters

### -param DeviceObject [in]


Pointer to the device object for the device. This parameter points to a <a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_device_object">DEVICE_OBJECT</a> system structure but is cast to type PVOID.

### -param DeviceProperty [in]

A <a href="/windows-hardware/drivers/ddi/wdm/ne-wdm-device_registry_property">DEVICE_REGISTRY_PROPERTY</a>-typed enumerator that identifies the device property to be retrieved.

### -param BufferLength [in]


Specifies the length in bytes of the buffer that is to receive the requested property data.

### -param PropertyBuffer [out]


Pointer to a caller-allocated buffer into which the method is to write the requested property data. The buffer must be large enough to contain the number of bytes specified in <i>BufferLength</i>.

### -param ResultLength [out]


Pointer to a caller-allocated variable into which the method outputs a count specifying the number of bytes actually written to the buffer. If the buffer size specified in <i>BufferLength</i> is too small to hold the property data, the method instead outputs the number of bytes required for the property data and returns STATUS_BUFFER_TOO_SMALL.

## -returns

<b>PcGetDeviceProperty</b> returns STATUS_SUCCESS if the call was successful. Otherwise, it returns an appropriate error code. The routine returns STATUS_BUFFER_TOO_SMALL if the buffer size specified in <i>BufferLength</i> was not large enough to contain the requested property data.

## -remarks

Two calls to <b>PcGetDeviceProperty</b> might be necessary to determine the required <i>BufferLength</i>. In the first call, <i>BufferLength</i> can either be zero or a best-guess estimate of the required buffer size. If the return status is STATUS_BUFFER_TOO_SMALL, this means that the caller should allocate a buffer of the size that was output through <i>ResultLength</i> and call <b>PcGetDeviceProperty</b> again.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_device_object">DEVICE_OBJECT</a>

<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-iogetdeviceproperty">IoGetDeviceProperty</a>

---
UID: NC:d3d10umddi.PFND3D10DDI_DESTROYSHADER
title: PFND3D10DDI_DESTROYSHADER (d3d10umddi.h)
description: The DestroyShader function destroys the specified shader object. The shader object can be destroyed only if it is not currently bound to a display device.
old-location: display\destroyshader.htm
ms.date: 05/10/2018
keywords: ["PFND3D10DDI_DESTROYSHADER callback function"]
ms.keywords: DestroyShader, DestroyShader callback function [Display Devices], PFND3D10DDI_DESTROYSHADER, PFND3D10DDI_DESTROYSHADER callback, UserModeDisplayDriverDx10_Functions_798387e4-b7c1-4b03-bef7-1dad6931b432.xml, d3d10umddi/DestroyShader, display.destroyshader
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
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
req.lib: 
req.dll: 
req.irql: 
targetos: Windows
tech.root: display
req.typenames: 
f1_keywords:
 - PFND3D10DDI_DESTROYSHADER
 - d3d10umddi/PFND3D10DDI_DESTROYSHADER
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3d10umddi.h
api_name:
 - PFND3D10DDI_DESTROYSHADER
---

# PFND3D10DDI_DESTROYSHADER callback function


## -description

The <i>DestroyShader</i> function destroys the specified shader object. The shader object can be destroyed only if it is not currently bound to a display device.

## -parameters

### -param unnamedParam1

*hDevice* [in]

A handle to the display device (graphics context).

### -param unnamedParam2

*hShader* [in]

A handle to the driver's private data for the shader object to destroy. The Microsoft Direct3D runtime will free the memory region that it previously allocated for the object. Therefore, the driver can no longer access this memory region.

## -remarks

The driver can use the <a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_seterror_cb">pfnSetErrorCb</a> callback function to set an error code. 



The driver should not encounter any error, except for <b>D3DDDIERR_DEVICEREMOVED</b>. Therefore, if the driver passes any error, except for <b>D3DDDIERR_DEVICEREMOVED</b>, in a call to the <a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_seterror_cb">pfnSetErrorCb</a> function, the Microsoft Direct3D runtime will determine that the error is critical. Even if the device was removed, the driver is not required to return <b>D3DDDIERR_DEVICEREMOVED</b>; however, if device removal interfered with the operation of <i>DestroyShader</i> (which typically should not happen), the driver can return <b>D3DDDIERR_DEVICEREMOVED</b>.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d10ddi_devicefuncs">D3D10DDI_DEVICEFUNCS</a>



<a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_seterror_cb">pfnSetErrorCb</a>


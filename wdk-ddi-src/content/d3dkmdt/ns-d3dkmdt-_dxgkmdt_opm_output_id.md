---
UID: NS:d3dkmdt._DXGKMDT_OPM_OUTPUT_ID
title: _DXGKMDT_OPM_OUTPUT_ID (d3dkmdt.h)
description: The DXGKMDT_OPM_OUTPUT_ID structure identifies the output connector.
old-location: display\dxgkmdt_opm_output_id.htm
tech.root: display
ms.date: 05/10/2018
keywords: ["DXGKMDT_OPM_OUTPUT_ID structure"]
ms.keywords: DXGKMDT_OPM_OUTPUT_ID, DXGKMDT_OPM_OUTPUT_ID structure [Display Devices], DmStructs_b0696fe6-3647-4a09-9817-578d4cfbf60a.xml, _DXGKMDT_OPM_OUTPUT_ID, d3dkmdt/DXGKMDT_OPM_OUTPUT_ID, display.dxgkmdt_opm_output_id
req.header: d3dkmdt.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 7
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
req.typenames: DXGKMDT_OPM_OUTPUT_ID
f1_keywords:
 - _DXGKMDT_OPM_OUTPUT_ID
 - d3dkmdt/_DXGKMDT_OPM_OUTPUT_ID
 - DXGKMDT_OPM_OUTPUT_ID
 - d3dkmdt/DXGKMDT_OPM_OUTPUT_ID
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dkmdt.h
api_name:
 - _DXGKMDT_OPM_OUTPUT_ID
 - DXGKMDT_OPM_OUTPUT_ID
---

# _DXGKMDT_OPM_OUTPUT_ID structure


## -description

The DXGKMDT_OPM_OUTPUT_ID structure identifies the output connector.

## -struct-fields

### -field rnRandomNumber

A <a href="/windows-hardware/drivers/ddi/d3dkmdt/ns-d3dkmdt-_dxgkmdt_opm_random_number">DXGKMDT_OPM_RANDOM_NUMBER</a> structure that contains a protected output object's 128-bit cryptographically secure random number. This random number is generated by an application and supplied to the display miniport driver in a call to the driver's <a href="/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_opm_get_information">DxgkDdiOPMGetInformation</a> function. This random number is supplied to the driver in the <b>rnRandomNumber</b> member of the <a href="/windows-hardware/drivers/ddi/d3dkmdt/ns-d3dkmdt-_dxgkmdt_opm_get_info_parameters">DXGKMDT_OPM_GET_INFO_PARAMETERS</a> structure.

### -field ulStatusFlags

A bitwise OR combination of the values from the <a href="/windows-hardware/drivers/ddi/d3dkmdt/ne-d3dkmdt-_dxgkmdt_opm_status">DXGKMDT_OPM_STATUS</a> enumeration that indicates the status of a protected output.

### -field OutputId

A UINT64 value that identifies the output connector.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3dkmdt/ns-d3dkmdt-_dxgkmdt_opm_get_info_parameters">DXGKMDT_OPM_GET_INFO_PARAMETERS</a>



<a href="/windows-hardware/drivers/ddi/d3dkmdt/ns-d3dkmdt-_dxgkmdt_opm_random_number">DXGKMDT_OPM_RANDOM_NUMBER</a>



<a href="/windows-hardware/drivers/ddi/dispmprt/nc-dispmprt-dxgkddi_opm_get_information">DxgkDdiOPMGetInformation</a>


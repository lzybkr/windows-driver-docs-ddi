---
UID: NE:d3dkmdt._DXGKMDT_OPM_ACP_PROTECTION_LEVEL
title: DXGKMDT_OPM_ACP_PROTECTION_LEVEL (d3dkmdt.h)
description: Learn more about the DXGKMDT_OPM_ACP_PROTECTION_LEVEL enumeration.
tech.root: display
ms.date: 05/17/2024
keywords: ["DXGKMDT_OPM_ACP_PROTECTION_LEVEL enumeration"]
ms.keywords: DXGKMDT_OPM_ACP_FORCE_ULONG, DXGKMDT_OPM_ACP_LEVEL_ONE, DXGKMDT_OPM_ACP_LEVEL_THREE, DXGKMDT_OPM_ACP_LEVEL_TWO, DXGKMDT_OPM_ACP_OFF, DXGKMDT_OPM_ACP_PROTECTION_LEVEL, DXGKMDT_OPM_ACP_PROTECTION_LEVEL enumeration [Display Devices], DmEnums_8ddb5546-7305-4b58-85e9-8e38a9bdf8af.xml, _DXGKMDT_OPM_ACP_PROTECTION_LEVEL, d3dkmdt/DXGKMDT_OPM_ACP_FORCE_ULONG, d3dkmdt/DXGKMDT_OPM_ACP_LEVEL_ONE, d3dkmdt/DXGKMDT_OPM_ACP_LEVEL_THREE, d3dkmdt/DXGKMDT_OPM_ACP_LEVEL_TWO, d3dkmdt/DXGKMDT_OPM_ACP_OFF, d3dkmdt/DXGKMDT_OPM_ACP_PROTECTION_LEVEL, display.dxgkmdt_opm_acp_protection_level
req.header: d3dkmdt.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows Vista
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
req.typenames: DXGKMDT_OPM_ACP_PROTECTION_LEVEL
f1_keywords:
 - _DXGKMDT_OPM_ACP_PROTECTION_LEVEL
 - d3dkmdt/_DXGKMDT_OPM_ACP_PROTECTION_LEVEL
 - DXGKMDT_OPM_ACP_PROTECTION_LEVEL
 - d3dkmdt/DXGKMDT_OPM_ACP_PROTECTION_LEVEL
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dkmdt.h
api_name:
 - _DXGKMDT_OPM_ACP_PROTECTION_LEVEL
 - DXGKMDT_OPM_ACP_PROTECTION_LEVEL
---

# DXGKMDT_OPM_ACP_PROTECTION_LEVEL enumeration


## -description

The DXGKMDT_OPM_ACP_PROTECTION_LEVEL enumeration indicates the protection levels for a protected output that supports Analog Copy Protection (ACP).

## -enum-fields

### -field DXGKMDT_OPM_ACP_OFF

Indicates that the signal from a video output is not protected by any form of ACP.

### -field DXGKMDT_OPM_ACP_LEVEL_ONE

Indicates that the signal from a video output is protected by the ACP level one protection scheme.

### -field DXGKMDT_OPM_ACP_LEVEL_TWO

Indicates that the signal from a video output is protected by the ACP level two protection scheme.

### -field DXGKMDT_OPM_ACP_LEVEL_THREE

Indicates that the signal from a video output is protected by the ACP level three protection scheme.

### -field DXGKMDT_OPM_ACP_FORCE_ULONG

Forces this enumeration to compile to 32 bits in size. Without this value, some compilers would allow this enumeration to compile to a size other than 32 bits. You should not use this value.

## -remarks

ACP protects analog TV signals. For example, a DVD player can use ACP to prevent a VCR from recording a copy of a DVD movie. Currently, OPM can use ACP to protect signals from composite outputs, S-Video outputs, or component outputs.

Display miniport drivers use the values in DXGKMDT_OPM_ACP_PROTECTION_LEVEL to report the virtual protection level of the protected output or the actual protection level of a physical connector through calls to the driver's [**DxgkDdiOPMGetInformation**](../dispmprt/nc-dispmprt-dxgkddi_opm_get_information.md) and [**DxgkDdiOPMGetCOPPCompatibleInformation**](../dispmprt/nc-dispmprt-dxgkddi_opm_get_copp_compatible_information.md) functions. The values in DXGKMDT_OPM_ACP_PROTECTION_LEVEL are also used to configure the protected output's new virtual protection level in a call to the driver's [**DxgkDdiOPMConfigureProtectedOutput**](../dispmprt/nc-dispmprt-dxgkddi_opm_configure_protected_output.md) function.

## -see-also

[**DXGKMDT_OPM_SET_PROTECTION_LEVEL_PARAMETERS**](ns-d3dkmdt-_dxgkmdt_opm_set_protection_level_parameters.md)

[**DXGKMDT_OPM_STANDARD_INFORMATION**](ns-d3dkmdt-_dxgkmdt_opm_standard_information.md)

[**DxgkDdiOPMConfigureProtectedOutput**](../dispmprt/nc-dispmprt-dxgkddi_opm_configure_protected_output.md)

[**DxgkDdiOPMGetCOPPCompatibleInformation**](../dispmprt/nc-dispmprt-dxgkddi_opm_get_copp_compatible_information.md)

[**DxgkDdiOPMGetInformation**](../dispmprt/nc-dispmprt-dxgkddi_opm_get_information.md)

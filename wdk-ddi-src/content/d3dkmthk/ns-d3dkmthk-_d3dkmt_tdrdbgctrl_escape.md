---
UID: NS:d3dkmthk._D3DKMT_TDRDBGCTRL_ESCAPE
title: D3DKMT_TDRDBGCTRL_ESCAPE (d3dkmthk.h)
description: Learn more about the D3DKMT_TDRDBGCTRL_ESCAPE structure.
ms.date: 07/17/2024
req.header: d3dkmthk.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
req.kmdf-ver: 
req.umdf-ver: 
req.lib: 
req.dll: 
req.ddi-compliance: 
req.unicode-ansi: 
req.max-support: 
req.typenames: D3DKMT_TDRDBGCTRL_ESCAPE
targetos: Windows
ms.custom: RS5
tech.root: display
f1_keywords:
 - _D3DKMT_TDRDBGCTRL_ESCAPE
 - d3dkmthk/_D3DKMT_TDRDBGCTRL_ESCAPE
 - D3DKMT_TDRDBGCTRL_ESCAPE
 - d3dkmthk/D3DKMT_TDRDBGCTRL_ESCAPE
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3dkmthk.h
api_name:
 - _D3DKMT_TDRDBGCTRL_ESCAPE
 - D3DKMT_TDRDBGCTRL_ESCAPE
dev_langs:
 - c++
---

# D3DKMT_TDRDBGCTRL_ESCAPE structure

## -description

The **D3DKMT_TDRDBGCTRL_ESCAPE** structure contains values for the (TDR) timeout detection and recovery escape process.

## -struct-fields

### -field TdrControl

The TDR control.

### -field NodeOrdinal

The node ordinal. This value is valid if the TdrControl is set to D3DKMT_TDRDBGCTRLTYPE_ENGINETDR.

## -remarks

## -see-also

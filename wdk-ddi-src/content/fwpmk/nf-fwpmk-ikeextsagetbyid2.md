---
UID: NF:fwpmk.IkeextSaGetById2
tech.root: netvista
title: IkeextSaGetById2
ms.date: 06/19/2024
targetos: Windows
description: The IkeextSaGetById2 function retrieves an IKE/AuthIP security association (SA) from the database.
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: fwpmk.h
req.idl: 
req.include-header: 
req.irql: <= PASSIVE_LEVEL
req.kmdf-ver: 
req.lib: fwpkclnt.lib
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: Available starting with Windows Vista.
req.target-min-winversvr: 
req.target-type: Universal
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - fwpmk.h
api_name:
 - IkeextSaGetById2
f1_keywords:
 - IkeextSaGetById2
 - fwpmk/IkeextSaGetById2
dev_langs:
 - c++
helpviewer_keywords:
 - IkeextSaGetById2
---

## -description

The **IkeextSaGetById2** function retrieves an IKE/AuthIP security association (SA) from the database.

## -parameters

### -param engineHandle [in]

Handle for an open session to the filter engine. Call **[FwpmEngineOpen0](nf-fwpmk-fwpmengineopen0.md)** to open a session to the filter engine.

### -param id [in]

The SA identifier.

### -param saLookupContext [in., optional]

Optional pointer to the SA lookup context propagated from the SA to data connections flowing over that SA. It is made available to any application that queries socket security properties using the Winsock API **[WSAQuerySocketSecurity](/windows/desktop/api/ws2tcpip/nf-ws2tcpip-wsaquerysocketsecurity)** function, allowing the application to obtain detailed IPsec authentication information for its connection.

### -param sa [out]

Address of the SA details.

## -returns

| Return code/value | Description |
|---|---|
| **ERROR_SUCCESS**<br>0 | The SA was retrieved successfully. |
| **FWP_E_\* error code**<br>0x80320001—0x80320039 | A Windows Filtering Platform (WFP) specific error. See [WFP Error Codes](/windows/win32/fwp/wfp-error-codes) for details. |
| **RPC_\* error code**<br>0x80010001—0x80010122 | Failure to communicate with the remote or local firewall engine. |
| **Other NTSTATUS codes** | An error occurred. |

## -remarks

The caller must free sa by a call to **[FwpmFreeMemory0](nf-fwpmk-fwpmfreememory0.md)**.

The caller needs [FWPM_ACTRL_READ](/windows/desktop/FWP/access-right-identifiers) access to the IKE/AuthIP security associations database. See [Access Control](/windows/desktop/FWP/access-control) for more information.

 **IkeextSaGetById1** is a specific implementation of **IkeextSaGetById**. See [WFP Version-Independent Names and Targeting Specific Versions of Windows](/windows/desktop/FWP/wfp-version-independent-names-and-targeting-specific-versions-of-windows) for more information.

## -see-also

- **[FwpmEngineOpen0](nf-fwpmk-fwpmengineopen0.md)**
- **[FwpmFreeMemory0](nf-fwpmk-fwpmfreememory0.md)**
- **[WSAQuerySocketSecurity](/windows/desktop/api/ws2tcpip/nf-ws2tcpip-wsaquerysocketsecurity)**
- [FWPM_ACTRL_READ](/windows/desktop/FWP/access-right-identifiers)
- [IKEEXT_SA_DETAILS2](/windows/desktop/api/iketypes/ns-iketypes-ikeext_sa_details2)
- [Access Control](/windows/desktop/FWP/access-control)
- [WFP Error Codes](/windows/win32/fwp/wfp-error-codes)
- [WFP Version-Independent Names and Targeting Specific Versions of Windows](/windows/desktop/FWP/wfp-version-independent-names-and-targeting-specific-versions-of-windows)
- [IKE/AuthIP Functions](/windows/desktop/FWP/fwp-ike-functions)
- [WFP Functions](/windows/desktop/FWP/fwp-functions)

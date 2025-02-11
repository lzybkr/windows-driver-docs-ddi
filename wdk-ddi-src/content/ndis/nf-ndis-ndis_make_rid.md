---
UID: NF:ndis.NDIS_MAKE_RID
title: NDIS_MAKE_RID macro (ndis.h)
description: The NDIS_MAKE_RID macro builds an NDIS_VF_RID value from PCI Express (PCIe) segment, bus, device, and function numbers. The miniport driver uses this value as a PCIe Requestor ID (RID) for a network adapter's PCIe Virtual Function (VF).
tech.root: netvista
ms.date: 04/16/2018
keywords: ["NDIS_MAKE_RID macro"]
ms.keywords: NDIS_MAKE_RID
req.header: ndis.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: Supported in NDIS 6.30 and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: 
req.dll: 
req.irql: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
returns-override: true
targetos: Windows
f1_keywords:
 - NDIS_MAKE_RID
 - ndis/NDIS_MAKE_RID
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ndis.h
api_name:
 - NDIS_MAKE_RID
---

# NDIS_MAKE_RID macro


## -description

The **NDIS_MAKE_RID** macro builds an NDIS_VF_RID value from PCI Express (PCIe) segment, bus, device, and function numbers. The miniport driver uses this value as a PCIe Requestor ID (RID) for a network adapter's PCIe Virtual Function (VF).

## -parameters

### -param _Segment

The PCIe segment number for the group of PCIe buses on which the device is attached. A PCIe segment is a set of PCIe buses that share configuration space.

### -param _Bus

The PCIe bus number of the bus on which the network adapter is attached.

### -param _Function

The function number of a logical device on the network adapter.

## -returns

NDIS_MAKE_RID returns an NDIS_VF_RID value that is constructed from the parameters.

## -remarks

When it handles an OID request of [OID_NIC_SWITCH_ALLOCATE_VF](/windows-hardware/drivers/network/oid-nic-switch-allocate-vf), the miniport driver for the PCIe Physical Function (PF) uses the **NDIS_MAKE_RID** macro to create a PCIe Requestor ID (RID) value for the VF. The driver retrieves the PCIe segment, bus, device, and function numbers for the VF by calling [**NdisMGetVirtualFunctionLocation**](nf-ndis-ndismgetvirtualfunctionlocation.md).

> [!NOTE]
> If an independent hardware vendor (IHV) provides a virtual bus driver (VBD) as part of its SR-IOV [driver package](/windows-hardware/drivers/install/driver-packages), its PF miniport driver must not call [**NdisMGetVirtualFunctionLocation**](nf-ndis-ndismgetvirtualfunctionlocation.md). Instead, the driver must interface with the VBD through a private communication channel, and request that the VBD call [*GetLocation*](../wdm/nc-wdm-get_virtual_device_location.md). This function is exposed from the [GUID_PCI_VIRTUALIZATION_INTERFACE](/windows-hardware/drivers/pci/) interface supported by the underlying PCI bus driver.

## -see-also

[**NdisMGetVirtualFunctionLocation**](nf-ndis-ndismgetvirtualfunctionlocation.md)

[OID_NIC_SWITCH_ALLOCATE_VF](/windows-hardware/drivers/network/oid-nic-switch-allocate-vf)

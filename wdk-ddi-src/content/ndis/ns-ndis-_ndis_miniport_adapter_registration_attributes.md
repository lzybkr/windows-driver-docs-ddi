---
UID: NS:ndis._NDIS_MINIPORT_ADAPTER_REGISTRATION_ATTRIBUTES
title: _NDIS_MINIPORT_ADAPTER_REGISTRATION_ATTRIBUTES (ndis.h)
description: An NDIS miniport driver sets up an NDIS_MINIPORT_ADAPTER_REGISTRATION_ATTRIBUTES structure to define registration attributes that are associated with a miniport adapter.
old-location: netvista\ndis_miniport_adapter_registration_attributes.htm
tech.root: netvista
ms.date: 05/02/2018
keywords: ["NDIS_MINIPORT_ADAPTER_REGISTRATION_ATTRIBUTES structure"]
ms.keywords: "*PNDIS_MINIPORT_ADAPTER_REGISTRATION_ATTRIBUTES, NDIS_MINIPORT_ADAPTER_REGISTRATION_ATTRIBUTES, NDIS_MINIPORT_ADAPTER_REGISTRATION_ATTRIBUTES structure [Network Drivers Starting with Windows Vista], PNDIS_MINIPORT_ADAPTER_REGISTRATION_ATTRIBUTES, PNDIS_MINIPORT_ADAPTER_REGISTRATION_ATTRIBUTES structure pointer [Network Drivers Starting with Windows Vista], _NDIS_MINIPORT_ADAPTER_REGISTRATION_ATTRIBUTES, miniport_structures_ref_e7ef8530-9b42-45a5-8d51-db76d399b437.xml, ndis/NDIS_MINIPORT_ADAPTER_REGISTRATION_ATTRIBUTES, ndis/PNDIS_MINIPORT_ADAPTER_REGISTRATION_ATTRIBUTES, netvista.ndis_miniport_adapter_registration_attributes"
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported in NDIS 6.0 and later.
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
req.typenames: NDIS_MINIPORT_ADAPTER_REGISTRATION_ATTRIBUTES, *PNDIS_MINIPORT_ADAPTER_REGISTRATION_ATTRIBUTES
f1_keywords:
 - _NDIS_MINIPORT_ADAPTER_REGISTRATION_ATTRIBUTES
 - ndis/_NDIS_MINIPORT_ADAPTER_REGISTRATION_ATTRIBUTES
 - PNDIS_MINIPORT_ADAPTER_REGISTRATION_ATTRIBUTES
 - ndis/PNDIS_MINIPORT_ADAPTER_REGISTRATION_ATTRIBUTES
 - NDIS_MINIPORT_ADAPTER_REGISTRATION_ATTRIBUTES
 - ndis/NDIS_MINIPORT_ADAPTER_REGISTRATION_ATTRIBUTES
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ndis.h
api_name:
 - _NDIS_MINIPORT_ADAPTER_REGISTRATION_ATTRIBUTES
 - PNDIS_MINIPORT_ADAPTER_REGISTRATION_ATTRIBUTES
 - NDIS_MINIPORT_ADAPTER_REGISTRATION_ATTRIBUTES
---

# _NDIS_MINIPORT_ADAPTER_REGISTRATION_ATTRIBUTES structure


## -description

An NDIS miniport driver sets up an <b>NDIS_MINIPORT_ADAPTER_REGISTRATION_ATTRIBUTES</b> structure to define
  registration attributes that are associated with a miniport adapter.

## -struct-fields

### -field Header

The type, revision, and size of the <b>NDIS_MINIPORT_ADAPTER_REGISTRATION_ATTRIBUTES</b> structure. This member is formatted as an <a href="/windows-hardware/drivers/ddi/objectheader/ns-objectheader-ndis_object_header">NDIS_OBJECT_HEADER</a> structure.

The miniport driver must set the <b>Type</b> member of <b>Header</b> to NDIS_OBJECT_TYPE_MINIPORT_ADAPTER_REGISTRATION_ATTRIBUTES. To specify the version of the <b>NDIS_MINIPORT_ADAPTER_REGISTRATION_ATTRIBUTES</b> structure, the driver must set the <b>Revision</b> member of <b>Header</b> to one of the following values: 





#### NDIS_MINIPORT_ADAPTER_REGISTRATION_ATTRIBUTES_REVISION_2

Added <b>AttributeFlags</b> flags for NDIS 6.30.

Set the <b>Size</b> member to NDIS_SIZEOF_MINIPORT_ADAPTER_REGISTRATION_ATTRIBUTES_REVISION_2.



#### NDIS_MINIPORT_ADAPTER_REGISTRATION_ATTRIBUTES_REVISION_1

Original version for NDIS 6.0.

Set the <b>Size</b> member to NDIS_SIZEOF_MINIPORT_ADAPTER_REGISTRATION_ATTRIBUTES_REVISION_1.

### -field MiniportAdapterContext

A handle to a context area that the miniport driver allocated in its 
     <a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_initialize">MiniportInitializeEx</a> function.
     The miniport driver uses this context area to maintain state information for a miniport adapter.

### -field AttributeFlags

A bitmask of flags that are combined with a bitwise OR. NDIS miniport drivers should set one or more of
     the following flags: 
     





#### NDIS_MINIPORT_ATTRIBUTES_HARDWARE_DEVICE

Set if the miniport driver directly controls a physical device. The physical device is assigned
       hardware resources such as interrupts, I/O ports, memory-mapped I/O, or DMA channels that the miniport
       driver should claim from the 
       <a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_initialize">
       MiniportInitializeEx</a> function.



#### NDIS_MINIPORT_ATTRIBUTES_NDIS_WDM

Set if the lower-level interface of the miniport adapter is a WDM bus driver such as USB or IEEE
       1394. In this case, the miniport driver does not allocate hardware resources such as I/O ports,
       interrupts, memory-mapped I/O, or DMA channels. Instead, the driver communicates with the device
       through the underlying bus driver's WDM interface.



#### NDIS_MINIPORT_ATTRIBUTES_BUS_MASTER

Set if the caller's NIC is a bus-master DMA device.



#### NDIS_MINIPORT_ATTRIBUTES_NO_HALT_ON_SUSPEND

Set if NDIS should not call a miniport driver's 
       <a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_halt">MiniportHaltEx</a> function before the
       system transitions to a low-power (sleeping) state. Drivers that rely on hardware-maintained state
       should not set this flag.



#### NDIS_MINIPORT_ATTRIBUTES_SURPRISE_REMOVE_OK

Set if the miniport driver can handle removal of its NIC without user notification. NDIS drivers receive
       surprise removal notifications at the 
       <a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_device_pnp_event_notify">
       MiniportDevicePnPEventNotify</a> function.



#### NDIS_MINIPORT_ATTRIBUTES_NOT_CO_NDIS

Set by a miniport driver that can support both connection-oriented and connectionless devices to indicate
       that the device is a connectionless device.



#### NDIS_MINIPORT_ATTRIBUTES_DO_NOT_BIND_TO_ALL_CO

Set by a CoNDIS miniport driver that does not provide TAPI services. Setting
       NDIS_MINIPORT_ATTRIBUTES_DO_NOT_BIND_TO_ALL_CO prevents NDIS from binding the miniport driver to the
       NDIS TAPI proxy driver (NDPROXY). By default, NDIS binds NDPROXY to all CoNDIS miniport
       drivers.



#### NDIS_MINIPORT_ATTRIBUTES_CONTROLS_DEFAULT_PORT

Set by a miniport driver that calls the 
       <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismnetpnpevent">NdisMNetPnPEvent</a> function to activate
       its default port. If NDIS_MINIPORT_ATTRIBUTES_CONTROLS_DEFAULT_PORT is not set, the default port is
       active. NDIS does not bind protocol drivers or attach filter modules to a miniport adapter if its
       default port is not active.



#### NDIS_MINIPORT_ATTRIBUTES_NO_PAUSE_ON_SUSPEND

Starting with NDIS 6.30, this flag is set if the miniport driver  is able to transition to a low-power state without being paused. 

For more information about this flag, see the Remarks section.

#### NDIS_MINIPORT_ATTRIBUTES_NO_OID_INTERCEPT_ON_NONDEFAULT_PORTS

Starting with NDIS 6.30, this flag is set if the miniport driver handles OIDs on non-default ports that are usually intercepted
       and handled by NDIS on its behalf. This does not change the behavior of OIDs destined to the default port.

#### NDIS_MINIPORT_ATTRIBUTES_REGISTER_BUGCHECK_CALLBACK

Starting with NDIS 6.30 miniports, NDIS will not invoke the miniport's MiniportShutdownEx handler during a BugCheck unless this flag is set.  Most miniports should not set this flag.

### -field CheckForHangTimeInSeconds

The time-out interval, in seconds, at which NDIS should call the 
     <a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_check_for_hang">
     MiniportCheckForHangEx</a> function. If a miniport driver has not responded to an OID request or a send request
     within two successive calls to 
     <i>MiniportCheckForHangEx</i>, NDIS can call the miniport driver's 
     <a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_reset">MiniportResetEx</a> function.
     

The  interval that NDIS uses when calling 
     <i>MiniportCheckForHangEx</i> is always a multiple of 2 seconds. For example, if you specify 5
     seconds, the interval will be approximately 4 seconds.

If this member is 0, the default time-out interval is 2 seconds.

<div class="alert"><b>Note</b>  The time-out interval must be greater than your miniport driver's initialization time. For more information, see <a href="/windows-hardware/drivers/network/miniport-adapter-check-for-hang-and-reset-operations">Miniport Adapter Check-for-Hang and Reset Operations</a>.</div>
<div> </div>

### -field InterfaceType

The I/O bus interface type of the miniport adapter. This is usually the type of I/O bus on which
     the miniport adapter is connected. The following values are supported in NDIS 6.0: 
     





#### NdisInterfaceInternal

Specifies a host-specific internal interface.



#### NdisInterfaceIsa

Specifies the ISA interface.



#### NdisInterfaceEisa

Specifies the extended ISA (EISA) interface. This interface type is not supported in NDIS 6.0
       and later versions.



#### NdisInterfaceMca

Refers to the MCA bus, which is no longer supported. This interface type is not supported in
       NDIS 6.0 and later versions.



#### NdisInterfaceTurboChannel

Specifies the Turbo Channel interface.



#### NdisInterfacePci

Specifies the Peripheral Component Interconnect (PCI) interface.



#### NdisInterfacePcMcia

Specifies the Personal Computer Memory Card International Association (PC Card)
       interface.



#### NdisInterfaceCBus

Specifies the CBus.



#### NdisInterfaceMPIBus

Specifies the MPIBus.



#### NdisInterfaceMPSABus

Specifies the MPSABus.



#### NdisInterfaceProcessorInternal

Specifies the processor internal bus.



#### NdisInterfaceInternalPowerBus

Specifies the internal power bus.



#### NdisInterfacePNPISABus

Specifies the PNPISABus.



#### NdisInterfacePNPBus

Specifies the PNPBus.

This parameter is irrelevant for intermediate drivers, which should specify 0 for this
     member.

## -remarks

A miniport driver passes a pointer to an NDIS_MINIPORT_ADAPTER_REGISTRATION_ATTRIBUTES structure in
    the 
    <i>MiniportAttributes</i> parameter of the 
    <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismsetminiportattributes">
    NdisMSetMiniportAttributes</a> function. A miniport driver calls 
    <b>NdisMSetMiniportAttributes</b> from its 
    <a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_initialize">MiniportInitializeEx</a> function
    during initialization.

Miniport drivers should set the attributes in NDIS_MINIPORT_ADAPTER_REGISTRATION_ATTRIBUTES as soon as
    possible within 
    <i>MiniportInitializeEx</i>. Setting these attributes is mandatory.

<h3><a id="NDIS_MINIPORT_ATTRIBUTES_NO_PAUSE_ON_SUSPEND_Flag"></a><a id="ndis_miniport_attributes_no_pause_on_suspend_flag"></a><a id="NDIS_MINIPORT_ATTRIBUTES_NO_PAUSE_ON_SUSPEND_FLAG"></a>NDIS_MINIPORT_ATTRIBUTES_NO_PAUSE_ON_SUSPEND Flag</h3>
NDIS issues an OID  request of <a href="/windows-hardware/drivers/network/oid-pnp-set-power">OID_PNP_SET_POWER</a> to the miniport driver before the underlying miniport adapter is transitioned to a low power state of D1, D2, or D3. When the driver handles this OID, it must prepare the miniport adapter for the transition to the lower power state and must not wait for the completion of pending receive packet indications.

In some cases, before NDIS issues the OID request of <a href="/windows-hardware/drivers/network/oid-pnp-set-power">OID_PNP_SET_POWER</a> to the miniport driver, NDIS calls the miniport driver's <a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_pause">MiniportPause</a> function as described below:

<ul>
<li>
If the <b>NDIS_MINIPORT_ATTRIBUTES_NO_PAUSE_ON_SUSPEND</b> flag is not set, NDIS   calls the miniport driver's <a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_pause">MiniportPause</a> function before the OID  request of <a href="/windows-hardware/drivers/network/oid-pnp-set-power">OID_PNP_SET_POWER</a> is issued to the driver. Within the context of the <i>MiniportPause</i> call, the driver must wait for the completion of pending receive packet indications.

</li>
<li>
If the <b>NDIS_MINIPORT_ATTRIBUTES_NO_PAUSE_ON_SUSPEND</b> flag is  set, NDIS does not call the miniport driver's <a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_pause">MiniportPause</a> function before the OID  request of <a href="/windows-hardware/drivers/network/oid-pnp-set-power">OID_PNP_SET_POWER</a> is issued to the driver.  When the miniport driver  handles the OID request, it must not assume that it had been previously paused when preparing the miniport adapter for the transition to a low-power state.

<div class="alert"><b>Note</b>  The exception to this occurs when a protocol or filter driver that supports NDIS 6.20 or earlier versions of NDIS is bound or attached to the miniport adapter. In this case, NDIS   calls the miniport driver's <a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_pause">MiniportPause</a> function regardless of whether the miniport driver sets the <b>NDIS_MINIPORT_ATTRIBUTES_NO_PAUSE_ON_SUSPEND</b> flag.</div>
<div> </div>
</li>
</ul>

## -see-also

<a href="/windows-hardware/drivers/network/miniport-adapter-check-for-hang-and-reset-operations">Miniport Adapter Check-for-Hang and Reset Operations</a>



<a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_check_for_hang">MiniportCheckForHangEx</a>



<a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_device_pnp_event_notify">
   MiniportDevicePnPEventNotify</a>



<a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_halt">MiniportHaltEx</a>



<a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_initialize">MiniportInitializeEx</a>



<a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_pause">MiniportPause</a>



<a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_reset">MiniportResetEx</a>



<a href="/windows-hardware/drivers/ddi/objectheader/ns-objectheader-ndis_object_header">NDIS_OBJECT_HEADER</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismnetpnpevent">NdisMNetPnPEvent</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismsetminiportattributes">NdisMSetMiniportAttributes</a>



<a href="/windows-hardware/drivers/network/oid-pnp-set-power">OID_PNP_SET_POWER</a>


---
description: "Learn more about: Universal Serial Bus (USB)"
UID: TP:usbref
title: Universal Serial Bus (USB)
ms.assetid: 3ef75da3-dd0a-3f40-b741-d6c381f1ed78
ms.date: 06/26/2024
keywords: ["Universal Serial Bus (USB)"]
ms.keywords: 
ms.topic: reference
---

# Universal Serial Bus (USB)

## -description

This reference section describes the driver programming interfaces that are included in the [Windows Driver Kit (WDK)](/windows-hardware/drivers/download-the-wdk). The programming interfaces are used for developing drivers that interact with USB devices, host controllers, and connectors. These interfaces include export functions that the drivers can call, callback routines that the driver can implement, I/O requests that the driver can send to the Microsoft-provided USB driver stack, and various data structures that are used in those requests.

For the programming guide, see [Universal Serial Bus (USB)](/windows-hardware/drivers/usbcon).

## Common USB client driver reference

A Windows Driver Model (WDM)-based USB client driver can call functions to communicate with the Microsoft-provided USB driver stack. These functions are defined in Usbdlib.h and the client driver requires the Usbdex.lib library. The library gets loaded and statically linked to the client driver module when built. A client driver that calls these routines can run on Windows Vista and later versions of Windows.

### Programming Guide

[Developing Windows client drivers for USB devices](/windows-hardware/drivers/usbcon/usb-driver-development-guide).

### Headers

- [usb.h](../usb/index.md)
- [usbbusif.h](../usbbusif/index.md)
- [usbdlib.h](../usbdlib/index.md)
- [usbfnattach.h](../usbfnattach/index.md)
- [usbfnbase.h](../usbfnbase/index.md)
- [usbfnioctl.h](../usbfnioctl/index.md)
- [usbioctl.h](../usbioctl/index.md)
- [usbspec.h](../usbspec/index.md)

## Deprecated functions, IOCTL requests for all USB drivers

These functions are deprecated.

>Do not use.

- USBD_CalculateUsbBandwidth
- USBD_CreateConfigurationRequest
- USBD_Debug_LogEntry
- USBD_GetUSBDIVersion
- USBD_ParseConfigurationDescriptor
- USBD_QueryBusTime
- USBD_RegisterHcFilter

These I/O requests are deprecated or reserved for internal use.

>USB client drivers must not use these I/O requests:

- IOCTL_USB_DIAG_IGNORE_HUBS_OFF
- IOCTL_USB_DIAG_IGNORE_HUBS_ON
- IOCTL_USB_DIAGNOSTIC_MODE_OFF
- IOCTL_USB_DIAGNOSTIC_MODE_ON
- IOCTL_USB_GET_HUB_CAPABILITIES
- IOCTL_USB_HCD_DISABLE_PORT
- IOCTL_USB_HCD_ENABLE_PORT
- IOCTL_USB_HCD_GET_STATS_1
- IOCTL_USB_HCD_GET_STATS_2
- IOCTL_USB_RESET_HUB

## Kernel-Mode IOCTLs

USB client drivers can receive or send any of the following I/O requests in kernel mode:

- [IOCTL_INTERNAL_USB_CYCLE_PORT](../usbioctl/ni-usbioctl-ioctl_internal_usb_cycle_port.md)
- [IOCTL_INTERNAL_USB_GET_BUS_INFO](../usbioctl/ni-usbioctl-ioctl_internal_usb_get_bus_info.md)
- [IOCTL_INTERNAL_USB_GET_CONTROLLER_NAME](../usbioctl/ni-usbioctl-ioctl_internal_usb_get_controller_name.md)
- [IOCTL_INTERNAL_USB_GET_DEVICE_CONFIG_INFO](../usbioctl/ni-usbioctl-ioctl_internal_usb_get_device_config_info.md)
- [IOCTL_INTERNAL_USB_GET_HUB_NAME](../usbioctl/ni-usbioctl-ioctl_internal_usb_get_hub_name.md)
- [IOCTL_INTERNAL_USB_GET_PORT_STATUS](../usbioctl/ni-usbioctl-ioctl_internal_usb_get_port_status.md)
- [IOCTL_INTERNAL_USB_GET_TOPOLOGY_ADDRESS](../usbioctl/ni-usbioctl-ioctl_internal_usb_get_topology_address.md)
- [IOCTL_INTERNAL_USB_REGISTER_COMPOSITE_DEVICE](../usbioctl/ni-usbioctl-ioctl_internal_usb_register_composite_device.md)
- [IOCTL_INTERNAL_USB_REQUEST_REMOTE_WAKE_NOTIFICATION](../usbioctl/ni-usbioctl-ioctl_internal_usb_request_remote_wake_notification.md)
- [IOCTL_INTERNAL_USB_RESET_PORT](../usbioctl/ni-usbioctl-ioctl_internal_usb_reset_port.md)
- [IOCTL_INTERNAL_USB_SUBMIT_IDLE_NOTIFICATION](../usbioctl/ni-usbioctl-ioctl_internal_usb_submit_idle_notification.md)
- [IOCTL_INTERNAL_USB_SUBMIT_URB](..//usbioctl/ni-usbioctl-ioctl_internal_usb_submit_urb.md)
- [IOCTL_INTERNAL_USB_UNREGISTER_COMPOSITE_DEVICE](../usbioctl/ni-usbioctl-ioctl_internal_usb_unregister_composite_device.md)

## User-Mode IOCTLs sent by applications and services

USB client drivers receive these user-mode I/O control requests at the kernel level:

- [IOCTL_GET_HCD_DRIVERKEY_NAME](../usbioctl/ni-usbioctl-ioctl_get_hcd_driverkey_name.md)
- [IOCTL_USB_GET_DESCRIPTOR_FROM_NODE_CONNECTION](../usbioctl/ni-usbioctl-ioctl_usb_get_descriptor_from_node_connection.md)
- [IOCTL_USB_GET_HUB_INFORMATION_EX](../usbioctl/ni-usbioctl-ioctl_usb_get_hub_information_ex.md)
- [IOCTL_USB_GET_NODE_CONNECTION_ATTRIBUTES](../usbioctl/ni-usbioctl-ioctl_usb_get_node_connection_attributes.md)
- [IOCTL_USB_GET_NODE_CONNECTION_DRIVERKEY_NAME](../usbioctl/ni-usbioctl-ioctl_usb_get_node_connection_driverkey_name.md)
- [IOCTL_USB_GET_NODE_CONNECTION_INFORMATION](../usbioctl/ni-usbioctl-ioctl_usb_get_node_connection_information.md)
- [IOCTL_USB_GET_NODE_CONNECTION_INFORMATION_EX](../usbioctl/ni-usbioctl-ioctl_usb_get_node_connection_information_ex.md)
- [IOCTL_USB_GET_NODE_CONNECTION_INFORMATION_EX_V2](../usbioctl/ni-usbioctl-ioctl_usb_get_node_connection_information_ex_v2.md)
- [IOCTL_USB_GET_NODE_CONNECTION_NAME](../usbioctl/ni-usbioctl-ioctl_usb_get_node_connection_name.md)
- [IOCTL_USB_GET_NODE_INFORMATION](../usbioctl/ni-usbioctl-ioctl_usb_get_node_information.md)
- [IOCTL_USB_GET_PORT_CONNECTOR_PROPERTIES](../usbioctl/ni-usbioctl-ioctl_usb_get_port_connector_properties.md)
- [IOCTL_USB_GET_ROOT_HUB_NAME](../usbioctl/ni-usbioctl-ioctl_usb_get_root_hub_name.md)
- [IOCTL_USB_HUB_CYCLE_PORT](../usbioctl/ni-usbioctl-ioctl_usb_hub_cycle_port.md)

## Dual-role controller driver reference

A USB driver for a dual-role controller can behave as a host controller or a function controller depending on the hardware. Dual-role controllers are common on mobile devices and allow for connections to PCs, as well as USB peripherals like keyboards and mice. A mobile device can behave as a peripheral when connected to a PC, allowing you to transfer files between your PC and the mobile device. In that scenario, the controller on the device operates in the function role. Conversely, the controller can operate in the host role when connected to USB peripherals like storage drives, keyboard, mice.

One of the main responsibilities of a driver for a dual-role controller is to switch between those two roles, tearing down the previous role's device node and loading the device node for the new role. When writing the driver, use the WDF class extension-client driver model. For more information about the WDF class extension-client driver model, see Ursdevice.h.

### Dual-role controller driver programming guide

For information about enabling a Windows system for USB dual-role support, see [USB Dual Role Driver Stack Architecture](/windows-hardware/drivers/usbcon/usb-dual-role-driver-stack-architecture).

### Dual-role controller driver headers

- [ursdevice.h](../ursdevice/index.md)
- [urstypes.h](../urstypes/index.md)

## Emulated host controller driver reference

Windows drivers can present non-USB devices as emulated USB devices. By using the WDF class extension-client driver model, you can write a driver that translates USB-level constructs (reset, data transfers) to the actual underlying bus by using the hardware's interface. The class extension and the client driver represent an emulated host controller with a root hub that is capable of presenting an attached device to the system as a USB device.

- USB device emulation class extension (UdeCx) is an in-box driver included Windows 10.
- The client driver written by an IHV/OEM and referred to as the UDE client driver.

The driver pair loads as the functional device object (FDO) in the host controller device stack. The UDE client driver communicates with Udecx by using a set of methods and event callback functions to handle device requests and notify the class extension about various events.

### Emulated host controller programming guide

- [Developing Windows drivers for emulated USB devices (UDE)](/windows-hardware/drivers/usbcon/developing-windows-drivers-for-emulated-usb-host-controllers-and-devices).

### Emulated host controller headers

- [udecxurb.h](../udecxurb/index.md)
- [udecxusbdevice.h](../udecxusbdevice/index.md)
- [udecxusbendpoint.h](../udecxusbendpoint/index.md)
- [udecxwdfdevice.h](../udecxwdfdevice/index.md)

## Function class driver reference

A USB function class driver implements the functionality of a specific group of interfaces on the USB device. The class driver handle requests issued by user mode services, or it can forwards requests to USB function class extension (UFX) and its function client driver. Certain class drivers are included in Windows, such as Media Transfer Protocol (MTP) and IpOverUsb. Windows also provides a generic kernel-mode class driver, GenericUSBFn.sys. If a particular interface or functionality isn't provided by a system-supplied driver, you might need to write a function class driver. You can implement the class driver as a kernel-mode driver by using Windows Driver Frameworks (WDF). Or you can implement it as a user-mode service. In that case, your class driver must be paired with the system-supplied class driver, GenericUSBFn.sys. For example, the MTP class driver runs as a user-mode service that transferring files to and from the device.

### Function class driver headers

- [usbfnbase.h](../usbfnbase/index.md)
- [usbfnioctl.h](../usbfnioctl/index.md)

## USB function controller client driver reference

The USB function client driver is responsible for implementing function controller-specific operations. The client driver communicates with the USB function class extension (UFX) module to handle endpoint data transfers, USB device state changes (reset, suspend, resume), attach/detach detection, port/charger detection. The client driver is also responsible for handling power management, and PnP events.

### USB function controller client driver programming guide

- [Write a USB function controller client driver](/windows-hardware/drivers/usbcon/function-client-driver)

### USB function controller client driver headers

- [ufxclient.h](../ufxclient/index.md)

## Filter driver for supporting USB chargers

Write a filter driver that supports detection of chargers, if the function controller uses the in-box Synopsys and ChipIdea drivers. If you're writing a client driver for a proprietary function controller, charger/attach detection is integrated in the client driver by implementing [EVT_UFX_DEVICE_PROPRIETARY_CHARGER_SET_PROPERTY](../ufxclient/nc-ufxclient-evt_ufx_device_proprietary_charger_set_property.md), [EVT_UFX_DEVICE_PROPRIETARY_CHARGER_RESET](../ufxclient/nc-ufxclient-evt_ufx_device_proprietary_charger_reset.md), and [EVT_UFX_DEVICE_DETECT_PROPRIETARY_CHARGER](../ufxclient/nc-ufxclient-evt_ufx_device_proprietary_charger_detect.md).

### Filter driver for supporting USB chargers programming guide

- [USB filter driver for supporting USB chargers](/windows-hardware/drivers/usbcon/usb-filter-driver-for-supporting-chargers)

### Filter driver for supporting USB chargers headers

- [usbfnattach.h](../usbfnattach/index.md)
- [ufxbase.h](../ufxbase/index.md)
- [ufxproprietarycharger.h](../ufxproprietarycharger/index.md)

## Host controller driver reference

The USB host controller extension is a system-supplied extension to the Kernel-Mode Driver Framework (KMDF). Within the Microsoft USB Driver Stack Architecture, USB host controller extension (UCX) provides functionality to assist a host controller client driver in managing a USB host controller device. The client driver handles hardware operations and events, power management, and PnP events. UCX serves as an abstracted interface to the rest of the Microsoft USB 3.0 stack, queues requests to the client driver, and performs other tasks.

If you're developing an xHCI host controller that isn't compliant with the specification, or developing a custom non-xHCI hardware (such as a virtual host controller), you can write a host controller driver that communicates with the UCX class extension.

### Host controller driver programming guide

[Developing Windows drivers for USB host controllers](/windows-hardware/drivers/usbcon/developing-windows-drivers-for-usb-host-controllers)

### Host controller driver headers

- [ucxclass.h](../ucxclass/index.md)
- [ucxcontroller.h](../ucxcontroller/index.md)
- [ucxendpoint.h](../ucxendpoint/index.md)
- [ucxroothub.h](../ucxroothub/index.md)
- [ucxsstreams.h](../ucxsstreams/index.md)
- [ucxusbdevice.h](../ucxusbdevice/index.md)

## Type-C driver reference

Windows 10 introduces support for the new USB connector: USB Type-C. You can write a driver for these scenarios:

| Scenario | Headers | Programming Guide |
|--|--|--|
| If your USB Type-C hardware has the capability of handling the power delivery (PD) state machine. | [ucmmanager.h](../ucmmanager/index.md) | [Write a USB Type-C connector driver](/windows-hardware/drivers/usbcon/bring-up-a-usb-type-c-connector-on-a-windows-system) |
| If your driver wants to participate in the policy decisions for USB Type-C connectors. | [Usbpmapi.h](../usbpmapi/index.md) | [Write a USB Type-C Policy Manager client driver](/windows-hardware/drivers/usbcon/policy-manager-client) |
| If your hardware doesn't support PD. | [ucmtcpcidevice.h](../ucmtcpcidevice/index.md)<br>[ucmtcpciglobals.h](../ucmtcpciglobals/index.md)<br>[ucmtcpciportcontroller.h](../ucmtcpciportcontroller/index.md)<br>[ucmtcpciportcontrollerrequests.h](../ucmtcpciportcontrollerrequests/index.md)<br>[ucmtypes.h](../ucmtypes/index.md) | [Write a USB Type-C port controller driver](/windows-hardware/drivers/usbcon/write-a-usb-type-c-port-controller-driver). |
| If your embedded controller is connected over non-ACPI transport | [Ucmucsicx.h](../ucmucsicx/index.md)<br>[Ucmucsidevice.h](../ucmucsidevice/index.md)<br>[Ucmucsifuncenum.h](../ucmucsifuncenum/index.md)<br>[Ucmucsiglobals.h](../ucmucsiglobals/index.md)<br>[Ucmucsippm.h](../ucmucsippm/index.md)<br>[Ucmucsippmrequests.h](../ucmucsippmrequests/index.md)<br>[Ucmucsispec.h](../ucmucsispec/index.md) | [Write a UCSI client driver](/windows-hardware/drivers/usbcon/write-a-ucsi-driver) |

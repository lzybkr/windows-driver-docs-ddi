---
UID: NI:mountmgr.IOCTL_MOUNTMGR_VOLUME_ARRIVAL_NOTIFICATION
title: IOCTL_MOUNTMGR_VOLUME_ARRIVAL_NOTIFICATION (mountmgr.h)
description: Learn about the IOCTL_MOUNTMGR_VOLUME_ARRIVAL_NOTIFICATION IOCTL.
tech.root: storage
ms.date: 06/04/2024
keywords: ["IOCTL_MOUNTMGR_VOLUME_ARRIVAL_NOTIFICATION IOCTL"]
ms.keywords: IOCTL_MOUNTMGR_VOLUME_ARRIVAL_NOTIFICATION, IOCTL_MOUNTMGR_VOLUME_ARRIVAL_NOTIFICATION control, IOCTL_MOUNTMGR_VOLUME_ARRIVAL_NOTIFICATION control code [Storage Devices], k307_7a15b0f1-9be7-476f-936c-225e39ef53c0.xml, mountmgr/IOCTL_MOUNTMGR_VOLUME_ARRIVAL_NOTIFICATION, storage.ioctl_mountmgr_volume_arrival_notification
req.header: mountmgr.h
req.include-header: Mountmgr.h
req.target-type: Windows
req.target-min-winverclnt: 
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
req.typenames: 
f1_keywords:
 - IOCTL_MOUNTMGR_VOLUME_ARRIVAL_NOTIFICATION
 - mountmgr/IOCTL_MOUNTMGR_VOLUME_ARRIVAL_NOTIFICATION
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Mountmgr.h
api_name:
 - IOCTL_MOUNTMGR_VOLUME_ARRIVAL_NOTIFICATION
---

## -description

This IOCTL allows a client to simulate a Plug and Play device interface arrival notification with the given volume name. If a client does not register a device interface of type MOUNTDEV_MOUNTED_DEVICE_GUID, the mount manager is not alerted of its arrival. However, the client can alert the mount manager of its volume's arrival directly by means of this IOCTL.

This IOCTL allows clients to obtain drive letters for newly created volumes during text mode setup when the Plug and Play device installer is not running.

Clients that have registered a device interface of type MOUNTDEV_MOUNTED_DEVICE_GUID in the normal way should not use this IOCTL.

## -ioctlparameters

### -ioctl-major-code

[IRP_MJ_DEVICE_CONTROL](/windows-hardware/drivers/kernel/irp-mj-device-control)

### -input-buffer

The mount manager client loads the following structure with the nonpersistent target device name. The initialized structure, [**MOUNTMGR_TARGET_NAME**](ns-mountmgr-_mountmgr_target_name.md) is inserted at the beginning of the buffer at **Irp->AssociatedIrp.SystemBuffer**.

### -input-buffer-length

**Parameters.DeviceIoControl.InputBufferLength** in the I/O stack location of the IRP indicates the size, in bytes, of the input buffer, which must be greater than or equal to ```sizeof(MOUNTMGR_TARGET_NAME)```.

### -output-buffer

None.

### -output-buffer-length

None.

### -in-out-buffer

N/A

### -inout-buffer-length

N/A

### -status-block

If the operation is successful, the **Status** field is set to STATUS_SUCCESS.

The input buffer size, indicated by **InputBufferLength**, must be large enough to hold the structure MOUNTMGR_TARGET_NAME and the symbolic link name that follows it. If it is not large enough, the **Status** field is set to STATUS_INVALID_PARAMETER.

## -remarks

For more information, see [Supporting Mount Manager Requests in a Storage Class Driver](/windows-hardware/drivers/storage/supporting-mount-manager-requests-in-a-storage-class-driver).

## -see-also

[**MOUNTMGR_TARGET_NAME**](ns-mountmgr-_mountmgr_target_name.md)

---
UID: NC:fltkernel.PFLT_INSTANCE_SETUP_CALLBACK
title: PFLT_INSTANCE_SETUP_CALLBACK (fltkernel.h)
description: A minifilter driver can register a routine of type PFLT_INSTANCE_SETUP_CALLBACK as the minifilter driver's InstanceSetupCallback routine.
old-location: ifsk\pflt_instance_setup_callback.htm
tech.root: ifsk
ms.date: 10/26/2021
keywords: ["PFLT_INSTANCE_SETUP_CALLBACK callback function"]
ms.keywords: FltCallbacks_c32f2452-6198-4e87-8566-6e219dcf2f28.xml, InstanceSetupCallback, InstanceSetupCallback routine [Installable File System Drivers], PFLT_INSTANCE_SETUP_CALLBACK, fltkernel/InstanceSetupCallback, ifsk.pflt_instance_setup_callback
req.header: fltkernel.h
req.include-header: Fltkernel.h
req.target-type: Desktop
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
req.irql: PASSIVE_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - PFLT_INSTANCE_SETUP_CALLBACK
 - fltkernel/PFLT_INSTANCE_SETUP_CALLBACK
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - fltkernel.h
api_name:
 - PFLT_INSTANCE_SETUP_CALLBACK
---

# PFLT_INSTANCE_SETUP_CALLBACK callback function

## -description

A minifilter driver can register a routine of type **PFLT_INSTANCE_SETUP_CALLBACK** as the minifilter driver's *InstanceSetupCallback* routine.

## -parameters

### -param FltObjects [in]

Pointer to an [FLT_RELATED_OBJECTS](ns-fltkernel-_flt_related_objects.md) structure that contains opaque pointers for the objects related to the current operation.

### -param Flags [in]

Bitmask of flags that indicate why the instance is being attached. Can be one or more of the following:

| Flag | Meaning |
| ---- | ------- |
| FLTFL_INSTANCE_SETUP_AUTOMATIC_ATTACHMENT (0x00000001) | The instance is being attached automatically. Either the minifilter driver was just loaded and is being attached to all existing volumes, or it is being attached to a newly mounted volume. |
| FLTFL_INSTANCE_SETUP_MANUAL_ATTACHMENT (0x00000002) | The instance is being attached manually because a user-mode application has called [FilterAttach](/windows/win32/api/fltuser/nf-fltuser-filterattach) or [FilterAttachAtAltitude](/windows/win32/api/fltuser/nf-fltuser-filterattachataltitude), or because a kernel-mode component has called [FltAttachVolume](nf-fltkernel-fltattachvolume.md) or [FltAttachVolumeAtAltitude](nf-fltkernel-fltattachvolumeataltitude.md) |
| FLTFL_INSTANCE_SETUP_NEWLY_MOUNTED_VOLUME (0x00000004) | The instance is being attached automatically to a newly mounted volume. |
| FLTFL_INSTANCE_SETUP_DETACHED_VOLUME (0x00000008) | The instance is being attached to a detached volume. It is possible, on some file systems (such as FAT and CDFS, which are used by some removable media drives), to reattach a volume after it has detached. A volume is detached if it has no associated storage stack. A volume in this state is usually a dismounted volume that still has open files. |
| FLTFL_INSTANCE_SETUP_DEV_VOLUME (0x00000010) | The instance is being attached to a volume that is formatted as a developer volume. File system filters can enable optimizations that don't require an administrator to trust the volume on a given machine. Available starting with Windows 11, version 22H2 September Update. |
| FLTFL_INSTANCE_SETUP_TRUSTED_VOLUME (0x00000020) | Indicates that an administrator on a given machine has trusted this volume and is willing to enable optimizations like not having anti-virus filters attach to the volume. This information is persisted in the registry on a given machine. This can be used by the file system filters to enable optimizations that require an administrator to trust the volume on a given machine. Available starting with Windows 11, version 22H2 September Update. |

### -param VolumeDeviceType [in]

[Device type](/windows-hardware/drivers/kernel/specifying-device-types) of the file system volume. Must be one of the following:

* FILE_DEVICE_CD_ROM_FILE_SYSTEM (0x00000003)
* FILE_DEVICE_DISK_FILE_SYSTEM (0x00000008)
* FILE_DEVICE_NETWORK_FILE_SYSTEM (0x00000014)

### -param VolumeFilesystemType [in]

File system type of the volume. The possible values are listed in [FLT_FILESYSTEM_TYPE](../fltuserstructures/ne-fltuserstructures-_flt_filesystem_type.md).

## -returns

This callback routine returns STATUS_SUCCESS or an NTSTATUS value such as the following:

| Return code | Description |
| ----------- | ----------- |
| STATUS_FLT_DO_NOT_ATTACH | Returning this value prevents the minifilter driver instance from being attached to the given volume. This is an error code. |

## -remarks

> [!NOTE]
> Do not perform any thread synchronization or inter-process communication in your **PFLT_INSTANCE_SETUP_CALLBACK** implementation. Performing such operations can lead to deadlock conditions.

When a minifilter driver registers itself by calling [**FltRegisterFilter**](nf-fltkernel-fltregisterfilter.md) from its [DriverEntry](../wdm/nc-wdm-driver_initialize.md) routine, it can register a routine of type **PFLT_INSTANCE_SETUP_CALLBACK** as the minifilter driver's *InstanceSetupCallback* routine.

To register the *InstanceSetupCallback* routine, the minifilter driver stores the address of a routine of type **PFLT_INSTANCE_SETUP_CALLBACK** in the **InstanceSetupCallback** member of the [**FLT_REGISTRATION**](ns-fltkernel-_flt_registration.md) structure that the minifilter driver passes as the **Registration** parameter of **FltRegisterFilter**.

The filter manager calls this routine on the first operation after a new volume is mounted.

The filter manager calls this routine to allow the minifilter driver to respond to an automatic or manual attachment request. If this routine returns an error or warning NTSTATUS code, the minifilter driver instance is not attached to the given volume. Otherwise, the minifilter driver instance is attached to the given volume.

## -see-also

[FLT_REGISTRATION](ns-fltkernel-_flt_registration.md)

[FLT_RELATED_OBJECTS](ns-fltkernel-_flt_related_objects.md)

[FilterAttach](/windows/win32/api/fltuser/nf-fltuser-filterattach)

[FilterAttachAtAltitude](/windows/win32/api/fltuser/nf-fltuser-filterattachataltitude)

[FltAttachVolume](nf-fltkernel-fltattachvolume.md)

[FltAttachVolumeAtAltitude](nf-fltkernel-fltattachvolumeataltitude.md)

[FltRegisterFilter](nf-fltkernel-fltregisterfilter.md)

[PFLT_INSTANCE_QUERY_TEARDOWN_CALLBACK](nc-fltkernel-pflt_instance_query_teardown_callback.md)

[PFLT_INSTANCE_TEARDOWN_CALLBACK](nc-fltkernel-pflt_instance_teardown_callback.md)

[Dev Drive](/windows/dev-drive/)

---
description: "Learn more about: Wdfdevice.h header"
UID: NA:wdfdevice
title: Wdfdevice.h header
ms.assetid: 24b2e402-56ef-3f36-b4f0-426a9d758500
ms.date: 05/09/2018
keywords: ["Wdfdevice.h header"]
ms.keywords: 
ms.topic: reference
tech.root: wdf
f1_keywords:
 - wdfdevice
 - wdfdevice/wdfdevice
api_name:
 - wdfdevice
---

# Wdfdevice.h header


## -description

This header is used by wdf. For more information, see:

- [Windows Driver Framework](../_wdf/index.md)
- [wdffdo.h header](../wdffdo/index.md)
- [wdfpdo.h header](../wdfpdo/index.md)

This topic orders the Windows Driver Frameworks (WDF) device object reference by category.

The categories on this page are:

- [General Framework Device Object Event Callback Functions](#general-framework-device-object-event-callback-functions)
- [General Framework Device Object Initialization Methods](#general-framework-device-object-initialization-methods)
- [General Framework Device Object Methods](#general-framework-device-object-methods)
- [General Framework Device Object Structures and Enumerations](#general-framework-device-object-structures-and-enumerations)
- [Initialization Functions for Device Object Structures](#initialization-functions-for-device-object-structures)

## General Framework Device Object Event Callback Functions

- [*EvtDeviceArmWakeFromS0*](./nc-wdfdevice-evt_wdf_device_arm_wake_from_s0.md)
- [*EvtDeviceArmWakeFromSx*](./nc-wdfdevice-evt_wdf_device_arm_wake_from_sx.md)
- [*EvtDeviceArmWakeFromSxWithReason*](./nc-wdfdevice-evt_wdf_device_arm_wake_from_sx_with_reason.md)
- [*EvtDeviceD0Entry*](./nc-wdfdevice-evt_wdf_device_d0_entry.md)
- [*EvtDeviceD0EntryPostInterruptsEnabled*](./nc-wdfdevice-evt_wdf_device_d0_entry_post_interrupts_enabled.md)
- [*EvtDeviceD0Exit*](./nc-wdfdevice-evt_wdf_device_d0_exit.md)
- [*EvtDeviceD0ExitPreInterruptsDisabled*](./nc-wdfdevice-evt_wdf_device_d0_exit_pre_interrupts_disabled.md)
- [*EvtDeviceDisarmWakeFromS0*](./nc-wdfdevice-evt_wdf_device_disarm_wake_from_s0.md)
- [*EvtDeviceDisarmWakeFromSx*](./nc-wdfdevice-evt_wdf_device_disarm_wake_from_sx.md)
- [*EvtDeviceFileCreate*](./nc-wdfdevice-evt_wdf_device_file_create.md)
- [*EvtDevicePnpStateChange*](./nc-wdfdevice-evt_wdf_device_pnp_state_change_notification.md)
- [*EvtDevicePowerPolicyStateChange*](./nc-wdfdevice-evt_wdf_device_power_policy_state_change_notification.md)
- [*EvtDevicePowerStateChange*](./nc-wdfdevice-evt_wdf_device_power_state_change_notification.md)
- [*EvtDevicePrepareHardware*](./nc-wdfdevice-evt_wdf_device_prepare_hardware.md)
- [*EvtDeviceQueryRemove*](./nc-wdfdevice-evt_wdf_device_query_remove.md)
- [*EvtDeviceQueryStop*](./nc-wdfdevice-evt_wdf_device_query_stop.md)
- [*EvtDeviceRelationsQuery*](./nc-wdfdevice-evt_wdf_device_relations_query.md)
- [*EvtDeviceReleaseHardware*](./nc-wdfdevice-evt_wdf_device_release_hardware.md)
- [*EvtDeviceSelfManagedIoCleanup*](./nc-wdfdevice-evt_wdf_device_self_managed_io_cleanup.md)
- [*EvtDeviceSelfManagedIoFlush*](./nc-wdfdevice-evt_wdf_device_self_managed_io_flush.md)
- [*EvtDeviceSelfManagedIoInit*](./nc-wdfdevice-evt_wdf_device_self_managed_io_init.md)
- [*EvtDeviceSelfManagedIoRestart*](./nc-wdfdevice-evt_wdf_device_self_managed_io_restart.md)
- [*EvtDeviceSelfManagedIoSuspend*](./nc-wdfdevice-evt_wdf_device_self_managed_io_suspend.md)
- [*EvtDeviceSurpriseRemoval*](./nc-wdfdevice-evt_wdf_device_surprise_removal.md)
- [*EvtDeviceUsageNotification*](./nc-wdfdevice-evt_wdf_device_usage_notification.md)
- [*EvtDeviceUsageNotificationEx*](./nc-wdfdevice-evt_wdf_device_usage_notification_ex.md)
- [*EvtDeviceWakeFromS0Triggered*](./nc-wdfdevice-evt_wdf_device_wake_from_s0_triggered.md)
- [*EvtDeviceWakeFromSxTriggered*](./nc-wdfdevice-evt_wdf_device_wake_from_sx_triggered.md)
- [*EvtDeviceWdmIrpDispatch*](./nc-wdfdevice-evt_wdfdevice_wdm_irp_dispatch.md)
- [*EvtDeviceWdmIrpPreprocess*](./nc-wdfdevice-evt_wdfdevice_wdm_irp_preprocess.md)
- [*EvtDeviceWdmPostPoFxRegisterDevice*](./nc-wdfdevice-evt_wdfdevice_wdm_post_po_fx_register_device.md)
- [*EvtDeviceWdmPrePoFxUnregisterDevice*](./nc-wdfdevice-evt_wdfdevice_wdm_pre_po_fx_unregister_device.md)
- [*EvtFileCleanup*](./nc-wdfdevice-evt_wdf_file_cleanup.md)
- [*EvtFileClose*](./nc-wdfdevice-evt_wdf_file_close.md)
- [*EvtIoInCallerContext*](./nc-wdfdevice-evt_wdf_io_in_caller_context.md)

## General Framework Device Object Initialization Methods

- [**WdfDeviceInitAssignName**](./nf-wdfdevice-wdfdeviceinitassignname.md)
- [**WdfDeviceInitAssignSDDLString**](./nf-wdfdevice-wdfdeviceinitassignsddlstring.md)
- [**WdfDeviceInitAssignWdmIrpPreprocessCallback**](./nf-wdfdevice-wdfdeviceinitassignwdmirppreprocesscallback.md)
- [**WdfDeviceInitFree**](./nf-wdfdevice-wdfdeviceinitfree.md)
- [**WdfDeviceInitRegisterPnpStateChangeCallback**](./nf-wdfdevice-wdfdeviceinitregisterpnpstatechangecallback.md)
- [**WdfDeviceInitRegisterPowerPolicyStateChangeCallback**](./nf-wdfdevice-wdfdeviceinitregisterpowerpolicystatechangecallback.md)
- [**WdfDeviceInitRegisterPowerStateChangeCallback**](./nf-wdfdevice-wdfdeviceinitregisterpowerstatechangecallback.md)
- [**WdfDeviceInitSetCharacteristics**](./nf-wdfdevice-wdfdeviceinitsetcharacteristics.md)
- [**WdfDeviceInitSetDeviceClass**](./nf-wdfdevice-wdfdeviceinitsetdeviceclass.md)
- [**WdfDeviceInitSetDeviceType**](./nf-wdfdevice-wdfdeviceinitsetdevicetype.md)
- [**WdfDeviceInitSetExclusive**](./nf-wdfdevice-wdfdeviceinitsetexclusive.md)
- [**WdfDeviceInitSetFileObjectConfig**](./nf-wdfdevice-wdfdeviceinitsetfileobjectconfig.md)
- [**WdfDeviceInitSetIoInCallerContextCallback**](./nf-wdfdevice-wdfdeviceinitsetioincallercontextcallback.md)
- [**WdfDeviceInitSetIoType**](./nf-wdfdevice-wdfdeviceinitsetiotype.md)
- [**WdfDeviceInitSetIoTypeEx**](./nf-wdfdevice-wdfdeviceinitsetiotypeex.md)
- [**WdfDeviceInitSetPnpPowerEventCallbacks**](./nf-wdfdevice-wdfdeviceinitsetpnppowereventcallbacks.md)
- [**WdfDeviceInitSetPowerInrush**](./nf-wdfdevice-wdfdeviceinitsetpowerinrush.md)
- [**WdfDeviceInitSetPowerNotPageable**](./nf-wdfdevice-wdfdeviceinitsetpowernotpageable.md)
- [**WdfDeviceInitSetPowerPageable**](./nf-wdfdevice-wdfdeviceinitsetpowerpageable.md)
- [**WdfDeviceInitSetPowerPolicyEventCallbacks**](./nf-wdfdevice-wdfdeviceinitsetpowerpolicyeventcallbacks.md)
- [**WdfDeviceInitSetPowerPolicyOwnership**](./nf-wdfdevice-wdfdeviceinitsetpowerpolicyownership.md)
- [**WdfDeviceInitSetReleaseHardwareOrderOnFailure**](./nf-wdfdevice-wdfdeviceinitsetreleasehardwareorderonfailure.md)
- [**WdfDeviceInitSetRemoveLockOptions**](./nf-wdfdevice-wdfdeviceinitsetremovelockoptions.md)
- [**WdfDeviceInitSetRequestAttributes**](./nf-wdfdevice-wdfdeviceinitsetrequestattributes.md)

## General Framework Device Object Methods

- [**WdfDeviceAddDependentUsageDeviceObject**](./nf-wdfdevice-wdfdeviceadddependentusagedeviceobject.md)
- [**WdfDeviceAddRemovalRelationsPhysicalDevice**](./nf-wdfdevice-wdfdeviceaddremovalrelationsphysicaldevice.md)
- [**WdfDeviceAllocAndQueryInterfaceProperty**](./nf-wdfdevice-wdfdeviceallocandqueryinterfaceproperty.md)
- [**WdfDeviceAllocAndQueryProperty**](./nf-wdfdevice-wdfdeviceallocandqueryproperty.md)
- [**WdfDeviceAllocAndQueryPropertyEx**](./nf-wdfdevice-wdfdeviceallocandquerypropertyex.md)
- [**WdfDeviceAssignInterfaceProperty**](./nf-wdfdevice-wdfdeviceassigninterfaceproperty.md)
- [**WdfDeviceAssignMofResourceName**](./nf-wdfdevice-wdfdeviceassignmofresourcename.md)
- [**WdfDeviceAssignProperty**](./nf-wdfdevice-wdfdeviceassignproperty.md)
- [**WdfDeviceAssignS0IdleSettings**](./nf-wdfdevice-wdfdeviceassigns0idlesettings.md)
- [**WdfDeviceAssignSxWakeSettings**](./nf-wdfdevice-wdfdeviceassignsxwakesettings.md)
- [**WdfDeviceClearRemovalRelationsDevices**](./nf-wdfdevice-wdfdeviceclearremovalrelationsdevices.md)
- [**WdfDeviceConfigureRequestDispatching**](./nf-wdfdevice-wdfdeviceconfigurerequestdispatching.md)
- [**WdfDeviceConfigureWdmIrpDispatchCallback**](./nf-wdfdevice-wdfdeviceconfigurewdmirpdispatchcallback.md)
- [**WdfDeviceCreate**](./nf-wdfdevice-wdfdevicecreate.md)
- [**WdfDeviceCreateDeviceInterface**](./nf-wdfdevice-wdfdevicecreatedeviceinterface.md)
- [**WdfDeviceCreateSymbolicLink**](./nf-wdfdevice-wdfdevicecreatesymboliclink.md)
- [**WdfDeviceEnqueueRequest**](./nf-wdfdevice-wdfdeviceenqueuerequest.md)
- [**WdfDeviceGetAlignmentRequirement**](./nf-wdfdevice-wdfdevicegetalignmentrequirement.md)
- [**WdfDeviceGetCharacteristics**](./nf-wdfdevice-wdfdevicegetcharacteristics.md)
- [**WdfDeviceGetDefaultQueue**](./nf-wdfdevice-wdfdevicegetdefaultqueue.md)
- [**WdfDeviceGetDevicePnpState**](./nf-wdfdevice-wdfdevicegetdevicepnpstate.md)
- [**WdfDeviceGetDevicePowerPolicyState**](./nf-wdfdevice-wdfdevicegetdevicepowerpolicystate.md)
- [**WdfDeviceGetDevicePowerState**](./nf-wdfdevice-wdfdevicegetdevicepowerstate.md)
- [**WdfDeviceGetDeviceStackIoType**](./nf-wdfdevice-wdfdevicegetdevicestackiotype.md)
- [**WdfDeviceGetDeviceState**](./nf-wdfdevice-wdfdevicegetdevicestate.md)
- [**WdfDeviceGetDriver**](./nf-wdfdevice-wdfdevicegetdriver.md)
- [**WdfDeviceGetFileObject**](./nf-wdfdevice-wdfdevicegetfileobject.md)
- [**WdfDeviceGetHardwareRegisterMappedAddress**](./nf-wdfdevice-wdfdevicegethardwareregistermappedaddress.md)
- [**WdfDeviceGetIoTarget**](./nf-wdfdevice-wdfdevicegetiotarget.md)
- [**WdfDeviceGetSystemPowerAction**](./nf-wdfdevice-wdfdevicegetsystempoweraction.md)
- [**WdfDeviceIndicateWakeStatus**](./nf-wdfdevice-wdfdeviceindicatewakestatus.md)
- [**WdfDeviceMapIoSpace**](./nf-wdfdevice-wdfdevicemapiospace.md)
- [**WdfDeviceMiniportCreate**](../wdfminiport/nf-wdfminiport-wdfdeviceminiportcreate.md)
- [**WdfDeviceOpenDevicemapKey**](./nf-wdfdevice-wdfdeviceopendevicemapkey.md)
- [**WdfDeviceOpenRegistryKey**](./nf-wdfdevice-wdfdeviceopenregistrykey.md)
- [**WdfDevicePostEvent**](./nf-wdfdevice-wdfdevicepostevent.md)
- [**WdfDeviceQueryInterfaceProperty**](./nf-wdfdevice-wdfdevicequeryinterfaceproperty.md)
- [**WdfDeviceQueryProperty**](./nf-wdfdevice-wdfdevicequeryproperty.md)
- [**WdfDeviceQueryPropertyEx**](./nf-wdfdevice-wdfdevicequerypropertyex.md)
- [**WdfDeviceReadFromHardware**](./nf-wdfdevice-wdfdevicereadfromhardware.md)
- [**WdfDeviceRemoveDependentUsageDeviceObject**](./nf-wdfdevice-wdfdeviceremovedependentusagedeviceobject.md)
- [**WdfDeviceRemoveRemovalRelationsPhysicalDevice**](./nf-wdfdevice-wdfdeviceremoveremovalrelationsphysicaldevice.md)
- [**WdfDeviceResumeIdle**](./nf-wdfdevice-wdfdeviceresumeidle.md)
- [**WdfDeviceResumeIdleWithTag**](/windows-hardware/drivers/wdf/wdfdeviceresumeidlewithtag)
- [**WdfDeviceRetrieveDeviceInterfaceString**](./nf-wdfdevice-wdfdeviceretrievedeviceinterfacestring.md)
- [**WdfDeviceRetrieveDeviceName**](./nf-wdfdevice-wdfdeviceretrievedevicename.md)
- [**WdfDeviceSetAlignmentRequirement**](./nf-wdfdevice-wdfdevicesetalignmentrequirement.md)
- [**WdfDeviceSetBusInformationForChildren**](./nf-wdfdevice-wdfdevicesetbusinformationforchildren.md)
- [**WdfDeviceSetCharacteristics**](./nf-wdfdevice-wdfdevicesetcharacteristics.md)
- [**WdfDeviceSetDeviceInterfaceState**](./nf-wdfdevice-wdfdevicesetdeviceinterfacestate.md)
- [**WdfDeviceSetDeviceState**](./nf-wdfdevice-wdfdevicesetdevicestate.md)
- [**WdfDeviceSetFailed**](./nf-wdfdevice-wdfdevicesetfailed.md)
- [**WdfDeviceSetPnpCapabilities**](./nf-wdfdevice-wdfdevicesetpnpcapabilities.md)
- [**WdfDeviceSetPowerCapabilities**](./nf-wdfdevice-wdfdevicesetpowercapabilities.md)
- [**WdfDeviceSetSpecialFileSupport**](./nf-wdfdevice-wdfdevicesetspecialfilesupport.md)
- [**WdfDeviceSetStaticStopRemove**](./nf-wdfdevice-wdfdevicesetstaticstopremove.md)
- [**WdfDeviceStopIdle**](./nf-wdfdevice-wdfdevicestopidle.md)
- [**WdfDeviceStopIdleWithTag**](/windows-hardware/drivers/wdf/wdfdevicestopidlewithtag)
- [**WdfDeviceUnmapIoSpace**](./nf-wdfdevice-wdfdeviceunmapiospace.md)
- [**WdfDeviceWdmAssignPowerFrameworkSettings**](./nf-wdfdevice-wdfdevicewdmassignpowerframeworksettings.md)
- [**WdfDeviceWdmDispatchIrp**](./nf-wdfdevice-wdfdevicewdmdispatchirp.md)
- [**WdfDeviceWdmDispatchIrpToIoQueue**](./nf-wdfdevice-wdfdevicewdmdispatchirptoioqueue.md)
- [**WdfDeviceWdmDispatchPreprocessedIrp**](./nf-wdfdevice-wdfdevicewdmdispatchpreprocessedirp.md)
- [**WdfDeviceWdmGetAttachedDevice**](./nf-wdfdevice-wdfdevicewdmgetattacheddevice.md)
- [**WdfDeviceWdmGetDeviceObject**](./nf-wdfdevice-wdfdevicewdmgetdeviceobject.md)
- [**WdfDeviceWdmGetPhysicalDevice**](./nf-wdfdevice-wdfdevicewdmgetphysicaldevice.md)
- [**WdfDeviceWriteToHardware**](./nf-wdfdevice-wdfdevicewritetohardware.md)
- [**WdfDevStateIsNP**](./nf-wdfdevice-wdfdevstateisnp.md)
- [**WdfDevStateNormalize**](./nf-wdfdevice-wdfdevstatenormalize.md)
- [**WdfWdmDeviceGetWdfDeviceHandle**](./nf-wdfdevice-wdfwdmdevicegetwdfdevicehandle.md)

## General Framework Device Object Structures and Enumerations

- [**WDF_DEVICE_FAILED_ACTION**](./ne-wdfdevice-_wdf_device_failed_action.md)
- [**WDF_DEVICE_INTERFACE_PROPERTY_DATA**](./ns-wdfdevice-_wdf_device_interface_property_data.md)
- [**WDF_DEVICE_IO_TYPE**](./ne-wdfdevice-_wdf_device_io_type.md)
- [**WDF_DEVICE_PNP_CAPABILITIES**](./ns-wdfdevice-_wdf_device_pnp_capabilities.md)
- [**WDF_DEVICE_PNP_NOTIFICATION_DATA**](./ns-wdfdevice-_wdf_device_pnp_notification_data.md)
- [**WDF_DEVICE_PNP_STATE**](./ne-wdfdevice-_wdf_device_pnp_state.md)
- [**WDF_DEVICE_POWER_CAPABILITIES**](./ns-wdfdevice-_wdf_device_power_capabilities.md)
- [**WDF_DEVICE_POWER_NOTIFICATION_DATA**](./ns-wdfdevice-_wdf_device_power_notification_data.md)
- [**WDF_DEVICE_POWER_POLICY_IDLE_SETTINGS**](./ns-wdfdevice-_wdf_device_power_policy_idle_settings.md)
- [**WDF_DEVICE_POWER_POLICY_NOTIFICATION_DATA**](./ns-wdfdevice-_wdf_device_power_policy_notification_data.md)
- [**WDF_DEVICE_POWER_POLICY_STATE**](./ne-wdfdevice-_wdf_device_power_policy_state.md)
- [**WDF_DEVICE_POWER_POLICY_WAKE_SETTINGS**](./ns-wdfdevice-_wdf_device_power_policy_wake_settings.md)
- [**WDF_DEVICE_POWER_STATE**](./ne-wdfdevice-_wdf_device_power_state.md)
- [**WDF_DEVICE_PROPERTY_DATA**](./ns-wdfdevice-_wdf_device_property_data.md)
- [**WDF_DEVICE_STATE**](./ns-wdfdevice-_wdf_device_state.md)
- [**WDF_DISPATCH_IRP_TO_IO_QUEUE_FLAGS**](./ne-wdfdevice-_wdf_dispatch_irp_to_io_queue_flags.md)
- [**WDF_EVENT_TYPE**](./ne-wdfdevice-_wdf_event_type.md)
- [**WDF_FILEOBJECT_CONFIG**](./ns-wdfdevice-_wdf_fileobject_config.md)
- [**WDF_IO_TYPE_CONFIG**](./ns-wdfdevice-_wdf_io_type_config.md)
- [**WDF_PNPPOWER_EVENT_CALLBACKS**](./ns-wdfdevice-_wdf_pnppower_event_callbacks.md)
- [**WDF_POWER_DEVICE_STATE**](./ne-wdfdevice-_wdf_power_device_state.md)
- [**WDF_POWER_FRAMEWORK_SETTINGS**](./ns-wdfdevice-_wdf_power_framework_settings.md)
- [**WDF_POWER_POLICY_EVENT_CALLBACKS**](./ns-wdfdevice-_wdf_power_policy_event_callbacks.md)
- [**WDF_POWER_POLICY_IDLE_TIMEOUT_CONSTANTS**](./ne-wdfdevice-_wdf_power_policy_idle_timeout_constants.md)
- [**WDF_POWER_POLICY_IDLE_TIMEOUT_TYPE**](./ne-wdfdevice-_wdf_power_policy_idle_timeout_type.md)
- [**WDF_POWER_POLICY_S0_IDLE_CAPABILITIES**](./ne-wdfdevice-_wdf_power_policy_s0_idle_capabilities.md)
- [**WDF_POWER_POLICY_S0_IDLE_USER_CONTROL**](./ne-wdfdevice-_wdf_power_policy_s0_idle_user_control.md)
- [**WDF_POWER_POLICY_SX_WAKE_USER_CONTROL**](./ne-wdfdevice-_wdf_power_policy_sx_wake_user_control.md)
- [**WDF_RELEASE_HARDWARE_ORDER_ON_FAILURE**](./ne-wdfdevice-_wdf_release_hardware_order_on_failure.md)
- [**WDF_REMOVE_LOCK_OPTIONS**](./ns-wdfdevice-_wdf_remove_lock_options.md)
- [**WDF_REMOVE_LOCK_OPTIONS_FLAGS**](./ne-wdfdevice-_wdf_remove_lock_options_flags.md)
- [**WDF_SPECIAL_FILE_TYPE**](./ne-wdfdevice-_wdf_special_file_type.md)
- [**WDF_STATE_NOTIFICATION_TYPE**](./ne-wdfdevice-_wdf_state_notification_type.md)
- [WDFDEVICE_INIT](/windows-hardware/drivers/wdf/wdfdevice_init)

## Initialization Functions for Device Object Structures

- [**WDF_DEVICE_INTERFACE_PROPERTY_DATA_INIT**](./nf-wdfdevice-wdf_device_interface_property_data_init.md)
- [**WDF_DEVICE_PNP_CAPABILITIES_INIT**](./nf-wdfdevice-wdf_device_pnp_capabilities_init.md)
- [**WDF_DEVICE_POWER_CAPABILITIES_INIT**](./nf-wdfdevice-wdf_device_power_capabilities_init.md)
- [**WDF_DEVICE_POWER_POLICY_IDLE_SETTINGS_INIT**](./nf-wdfdevice-wdf_device_power_policy_idle_settings_init.md)
- [**WDF_DEVICE_POWER_POLICY_WAKE_SETTINGS_INIT**](./nf-wdfdevice-wdf_device_power_policy_wake_settings_init.md)
- [**WDF_DEVICE_PROPERTY_DATA_INIT**](./nf-wdfdevice-wdf_device_property_data_init.md)
- [**WDF_DEVICE_STATE_INIT**](./nf-wdfdevice-wdf_device_state_init.md)
- [**WDF_FILEOBJECT_CONFIG_INIT**](./nf-wdfdevice-wdf_fileobject_config_init.md)
- [**WDF_IO_TYPE_CONFIG_INIT**](./nf-wdfdevice-wdf_io_type_config_init.md)
- [**WDF_PNPPOWER_EVENT_CALLBACKS_INIT**](./nf-wdfdevice-wdf_pnppower_event_callbacks_init.md)
- [**WDF_POWER_FRAMEWORK_SETTINGS_INIT**](./nf-wdfdevice-wdf_power_framework_settings_init.md)
- [**WDF_POWER_POLICY_EVENT_CALLBACKS_INIT**](./nf-wdfdevice-wdf_power_policy_event_callbacks_init.md)
- [**WDF_REMOVE_LOCK_OPTIONS_INIT**](./nf-wdfdevice-wdf_remove_lock_options_init.md)


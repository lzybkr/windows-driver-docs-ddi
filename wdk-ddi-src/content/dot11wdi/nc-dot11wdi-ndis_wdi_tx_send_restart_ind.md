---
UID: NC:dot11wdi.NDIS_WDI_TX_SEND_RESTART_IND
title: NDIS_WDI_TX_SEND_RESTART_IND (dot11wdi.h)
description: The NdisWdiTxSendRestartIndication callback function resumes transmission on a given port to a given peer or peer-TID combination.
old-location: netvista\ndiswditxsendrestartindication.htm
tech.root: netvista
ms.date: 09/07/2022
keywords: ["NDIS_WDI_TX_SEND_RESTART_IND callback function"]
ms.keywords: NDIS_WDI_TX_SEND_RESTART_IND, NDIS_WDI_TX_SEND_RESTART_IND callback, NdisWdiTxSendRestartIndication, NdisWdiTxSendRestartIndication callback function [Network Drivers Starting with Windows Vista], dot11wdi/NdisWdiTxSendRestartIndication, netvista.ndiswditxsendrestartindication
req.header: dot11wdi.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
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
 - NDIS_WDI_TX_SEND_RESTART_IND
 - dot11wdi/NDIS_WDI_TX_SEND_RESTART_IND
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - dot11wdi.h
api_name:
 - NDIS_WDI_TX_SEND_RESTART_IND
---

# NDIS_WDI_TX_SEND_RESTART_IND callback function


## -description

> [!IMPORTANT]
> This topic is part of the [WDI driver model](/windows-hardware/drivers/network/wdi-miniport-driver-design-guide) released in Windows 10. The WDI driver model is in maintenance mode and will only receive high priority fixes. [WiFiCx](/windows-hardware/drivers/netcx/wifi-wdf-class-extension-wificx) is the Wi-Fi driver model released in Windows 11. We recommend that you use WiFiCx to take advantage of the latest  features.

The NdisWdiTxSendRestartIndication callback function resumes transmission on a given port to a given peer or peer-TID combination.

This is a callback inside <a href="/windows-hardware/drivers/ddi/dot11wdi/ns-dot11wdi-_ndis_wdi_data_api">NDIS_WDI_DATA_API</a>.

## -parameters

### -param NdisMiniportDataPathHandle [in]


The NdisMiniportDataPathHandle passed to the IHV miniport in <a href="/windows-hardware/drivers/ddi/dot11wdi/nc-dot11wdi-miniport_wdi_tal_txrx_initialize">MiniportWdiTalTxRxInitialize</a>.

### -param PortId [in]


The port ID. Wildcards are accepted.

### -param PeerId [in]


The peer ID. Wildcards are accepted.

### -param ExTidBitmask [in]


The Extended TID bitmask. See <i>Remarks</i> section for more information.

### -param TxRestartReason [in]

TX restart reason bitmask, specified as <a href="/windows-hardware/drivers/ddi/dot11wdi/ne-dot11wdi-_wdi_tx_pause_reason">WDI_TX_PAUSE_REASON</a> value(s). See <i>Remarks</i> section for more information.

## -remarks

In the <i>ExTidBitmask</i> parameter, the <i>i</i><sup>th</sup> bit represents extended TID <i>i </i>(the least significant bit is bit 0) .

The <a href="/windows-hardware/drivers/ddi/dot11wdi/ne-dot11wdi-_wdi_tx_pause_reason">WDI_TX_PAUSE_REASON</a> bitmask may contain a set of pause reasons. The pauses reasons are cumulative, so an <a href="/windows-hardware/drivers/ddi/dot11wdi/nc-dot11wdi-ndis_wdi_tx_send_pause_ind">NdisWdiTxSendPauseIndication</a> with a pause reason of <b>WDI_TX_PAUSE_REASON_CREDIT</b> followed by an <i>NdisWdiTxSendPauseIndication</i> with a pause reason of <b>WDI_TX_PAUSE_REASON_IHV1</b> requires an <i>NdisWdiTxSendRestartIndication</i> with a pause reason of (<b>WDI_TX_PAUSE_REASON_CREDIT</b> | <b>WDI_TX_PAUSE_REASON_IHV1</b>) for the set of queues to be unpaused.

If the pause reason is <b>WDI_TX_PAUSE_REASON_PS</b>, the TAL/target does not issue an <i>NdisWdiTxSendRestartIndication</i> to any of the affected queues until it has received an <a href="/windows-hardware/drivers/ddi/dot11wdi/nc-dot11wdi-miniport_wdi_tx_tal_queue_in_order">MiniportWdiTxTalQueueInOrder</a> notification for that queue.
<i>NdisWdiTxSendRestartIndication</i> does not resume a queue if the queue has no remaining pause reason bits set after applying the restart reason bitmask.

If <b>TargetPriorityQueueing</b> is true, <a href="/windows-hardware/drivers/network/wdi-peer-id">WDI_PEER_ID</a> must be a wildcard.  Only port or adapter restarts are allowed in this mode.

## -see-also

<a href="/windows-hardware/drivers/ddi/dot11wdi/ns-dot11wdi-_ndis_wdi_data_api">NDIS_WDI_DATA_API</a>



<a href="/windows-hardware/drivers/ddi/dot11wdi/nc-dot11wdi-ndis_wdi_tx_send_pause_ind">NdisWdiTxSendPauseIndication</a>



<a href="/windows-hardware/drivers/network/wdi-peer-id">WDI_PEER_ID</a>



<a href="/windows-hardware/drivers/network/wdi-port-id">WDI_PORT_ID</a>



<a href="/windows-hardware/drivers/ddi/dot11wdi/ns-dot11wdi-_wdi_txrx_target_capabilities">WDI_TXRX_CAPABILITIES</a>



<a href="/windows-hardware/drivers/ddi/dot11wdi/ne-dot11wdi-_wdi_tx_pause_reason">WDI_TX_PAUSE_REASON</a>


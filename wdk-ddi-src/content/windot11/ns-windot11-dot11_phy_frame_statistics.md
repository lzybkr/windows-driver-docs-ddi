---
UID: NS:windot11.DOT11_PHY_FRAME_STATISTICS
title: DOT11_PHY_FRAME_STATISTICS (windot11.h)
description: The DOT11_PHY_FRAME_STATISTICS structure is part of the Native 802.11 Wireless LAN interface, which is deprecated for Windows 10 and later.
old-location: netvista\dot11_phy_frame_statistics.htm
tech.root: netvista
ms.date: 02/16/2018
keywords: ["DOT11_PHY_FRAME_STATISTICS structure"]
ms.keywords: "*PDOT11_PHY_FRAME_STATISTICS, DOT11_PHY_FRAME_STATISTICS, DOT11_PHY_FRAME_STATISTICS structure [Network Drivers Starting with Windows Vista], Native_802.11_data_types_e7446fc8-9a7c-41c5-bf90-7988dfddc950.xml, PDOT11_PHY_FRAME_STATISTICS, PDOT11_PHY_FRAME_STATISTICS structure pointer [Network Drivers Starting with Windows Vista], netvista.dot11_phy_frame_statistics, windot11/DOT11_PHY_FRAME_STATISTICS, windot11/PDOT11_PHY_FRAME_STATISTICS"
req.header: windot11.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating   systems.
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
req.typenames: DOT11_PHY_FRAME_STATISTICS, *PDOT11_PHY_FRAME_STATISTICS
f1_keywords:
 - DOT11_PHY_FRAME_STATISTICS
 - windot11/DOT11_PHY_FRAME_STATISTICS
 - PDOT11_PHY_FRAME_STATISTICS
 - windot11/PDOT11_PHY_FRAME_STATISTICS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - windot11.h
api_name:
 - DOT11_PHY_FRAME_STATISTICS
 - PDOT11_PHY_FRAME_STATISTICS
---

# DOT11_PHY_FRAME_STATISTICS structure


## -description

> [!Important]
> [WiFiCx](/windows-hardware/drivers/netcx/wifi-wdf-class-extension-wificx) is the new Wi-Fi driver model released in Windows 11. We recommend that you use WiFiCx to take advantage of the latest features. The WDI driver model is now in maintenance mode and will only receive high priority fixes.

The DOT11_PHY_FRAME_STATISTICS structure records statistical counters for the IEEE physical (PHY)
  layer of the 802.11 station.

## -struct-fields

### -field ullTransmittedFrameCount

The number of MSDU packets and MMPDU frames that the IEEE PHY layer of the 802.11 station has
     successfully transmitted.

### -field ullMulticastTransmittedFrameCount

The number of multicast or broadcast MSDU packets and MMPDU frames that the IEEE PHY layer of the
     802.11 station has successfully transmitted.

### -field ullFailedCount

The number of MSDU packets and MMPDU frames that the 802.11 station failed to transmit after
     exceeding the retry limits defined by the 802.11 IEEE
     <b>dot11ShortRetryLimit</b> or
     <b>dot11LongRetryLimit</b> MIB counters. For more information about these MIB counters, see
     <a href="/windows-hardware/drivers/network/oid-dot11-short-retry-limit">OID_DOT11_SHORT_RETRY_LIMIT</a> or
     <a href="/windows-hardware/drivers/network/oid-dot11-long-retry-limit">OID_DOT11_LONG_RETRY_LIMIT</a>.

### -field ullRetryCount

The number of MSDU packets and MMPDU frames that the 802.11 station successfully transmitted after
     one or more attempts.

### -field ullMultipleRetryCount

The number of MSDU packets and MMPDU frames that the 802.11 station successfully transmitted after
     more than one retransmission attempt.


For MSDU packets, the miniport driver must increment this counter for each packet that was
     transmitted successfully after one or more of its MPDU fragments required retransmission.

### -field ullMaxTXLifetimeExceededCount

The number of MSDU packets and MMPDU frames that the 802.11 station failed to transmit because of
     a timeout as defined by the IEEE 802.11
     <b>dot11MaxTransmitMSDULifetime</b> MIB object. For more information about this MIB object, see
     <a href="/windows-hardware/drivers/network/oid-dot11-max-transmit-msdu-lifetime">
     OID_DOT11_MAX_TRANSMIT_MSDU_LIFETIME</a>.

### -field ullTransmittedFragmentCount

The number of MPDU frames that the 802.11 station transmitted and acknowledged through a received
     802.11 ACK frame.

### -field ullRTSSuccessCount

The number of times that the 802.11 station received a Clear To Send (CTS) frame in response to a
     Request To Send (RTS) frame.

### -field ullRTSFailureCount

The number of times that the 802.11 station did not receive a CTS frame in response to an RTS
     frame.

### -field ullACKFailureCount

The number of times that the 802.11 station expected and did not receive an Acknowledgement (ACK)
     frame.

### -field ullReceivedFrameCount

The total number of MSDU packets and MMPDU frames that the 802.11 station has successfully
     received.


For MSDU packets, the miniport driver must increment this counter for each packet whose MPDU
     fragments were received and passed frame check sequence (FCS) verification and replay detection. The
     miniport driver must increment this member regardless of whether the received MSDU packet or MPDU
     fragment fail MAC-layer cipher decryption.

This counter is optional. If the NIC does not support this counter, the miniport driver should set
     this member to DOT11_STATISTICS_UNKNOWN.

### -field ullMulticastReceivedFrameCount

The number of multicast or broadcast MSDU packets and MMPDU frames that the 802.11 station has
     successfully received.


For MSDU packets, the miniport driver must increment this counter for each packet whose MPDU
     fragments were received and passed FCS verification and replay detection. The miniport driver must
     increment this member regardless of whether the received MSDU packet or MPDU fragment fail MAC-layer
     cipher decryption.

This counter is optional. If the NIC does not support this counter, the miniport driver should set
     this member to DOT11_STATISTICS_UNKNOWN.

### -field ullPromiscuousReceivedFrameCount

The number of MSDU packets or MMPDU frames received by the 802.11 station when a promiscuous
     packet filter is enabled. For more information about packet filters, see
     <a href="/windows-hardware/drivers/network/oid-gen-current-packet-filter">OID_GEN_CURRENT_PACKET_FILTER</a>.


If a promiscuous packet filter is enabled, the miniport driver must only increment this counter for
     received MSDU packets or MMPDU frames that would have been rejected if the filter was not enabled. The
     driver must not increment this counter for:

<ul>
<li>
Unicast MSDU packets or MMPDU frames with a destination MAC address that matches the 802.11
       station's MAC address.

</li>
<li>
Multicast or broadcast MSDU packets or MMPDU frames with a destination MAC address that matches an
       entry in the multicast address list of the 802.11 station. For more information about the multicast
       address list, see
       <a href="/windows-hardware/drivers/network/oid-dot11-multicast-list">OID_DOT11_MULTICAST_LIST</a>.

</li>
</ul>

### -field ullMaxRXLifetimeExceededCount

The number if MSDU packets and MMPDU frames that the 802.11 station discarded because of a timeout
     as defined by the IEEE 802.11
     <b>dot11MaxReceiveLifetime</b> MIB object. For more information about this MIB object, see
     <a href="/windows-hardware/drivers/network/oid-dot11-max-receive-lifetime">
     OID_DOT11_MAX_RECEIVE_LIFETIME</a>.

### -field ullFrameDuplicateCount

The number of duplicate MPDU frames that the 802.11 station received. The 802.11 station
     determines duplicate frames through the Sequence Control field of the 802.11 MAC header.

### -field ullReceivedFragmentCount

The number of MPDU frames received by the 802.11 station for MSDU packets or MMPDU frames.

### -field ullPromiscuousReceivedFragmentCount

The number of MPDU frames received by the 802.11 station for MSDU packets or MMPDU frames when a
     promiscuous packet filter was enabled. For more information about packet filters, see
     <a href="/windows-hardware/drivers/network/oid-gen-current-packet-filter">OID_GEN_CURRENT_PACKET_FILTER</a>.


If a promiscuous packet filter is enabled, the miniport driver must only increment this counter for
     received MPDU frames that would have been rejected if the filter was not enabled. The driver must not
     increment this counter for:

<ul>
<li>
Unicast MPDU frames with a destination MAC address that matches the 802.11 station's MAC
       address.

</li>
<li>
Multicast or broadcast MPDU frames with a destination MAC address that matches an entry in the
       multicast address list of the 802.11 station. For more information about the multicast address list,
       see
       <a href="/windows-hardware/drivers/network/oid-dot11-multicast-list">OID_DOT11_MULTICAST_LIST</a>.

</li>
</ul>

### -field ullFCSErrorCount

The number of MPDU frames that the 802.11 station received with FCS errors.

## -syntax

```cpp
typedef struct DOT11_PHY_FRAME_STATISTICS {
  ULONGLONG ullTransmittedFrameCount;
  ULONGLONG ullMulticastTransmittedFrameCount;
  ULONGLONG ullFailedCount;
  ULONGLONG ullRetryCount;
  ULONGLONG ullMultipleRetryCount;
  ULONGLONG ullMaxTXLifetimeExceededCount;
  ULONGLONG ullTransmittedFragmentCount;
  ULONGLONG ullRTSSuccessCount;
  ULONGLONG ullRTSFailureCount;
  ULONGLONG ullACKFailureCount;
  ULONGLONG ullReceivedFrameCount;
  ULONGLONG ullMulticastReceivedFrameCount;
  ULONGLONG ullPromiscuousReceivedFrameCount;
  ULONGLONG ullMaxRXLifetimeExceededCount;
  ULONGLONG ullFrameDuplicateCount;
  ULONGLONG ullReceivedFragmentCount;
  ULONGLONG ullPromiscuousReceivedFragmentCount;
  ULONGLONG ullFCSErrorCount;
} DOT11_PHY_FRAME_STATISTICS, *PDOT11_PHY_FRAME_STATISTICS;
```

## -remarks

The members of this structure are used to record PHY-level statistics for:

<ul>
<li>
802.11 MSDU packets.

</li>
<li>
802.11 MMPDU frames.

</li>
<li>
802.11 MPDU frames. MPDU frame counters must include all MPDU fragments sent for an MSDU packet or
      MMPDU frame

</li>
</ul>

## -see-also

<a href="/windows-hardware/drivers/network/extensible-station-phy-statistics">Extensible Station PHY
   Statistics</a>



<a href="/windows-hardware/drivers/network/oid-dot11-statistics">OID_DOT11_STATISTICS</a>



<a href="..\windot11\ns-windot11-dot11_statistics.md">DOT11_STATISTICS</a>



<a href="/windows-hardware/drivers/network/native-802-11-statistics">Native 802.11 Statistics</a>


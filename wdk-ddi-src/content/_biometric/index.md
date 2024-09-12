---
description: "Learn more about: Biometric"
UID: TP:biometric
title: Biometric overview
ms.assetid: 5af9b578-0fef-3edc-b459-8e62ce9c45f8
ms.date: 05/09/2018
keywords: ["Biometric"]
ms.keywords:
ms.topic: reference
---

# Biometric

## -description

Windows 7 and later implement support for Biometric devices. The Windows Biometric Framework (WBF) is a generic biometric architecture in Windows 7 and later versions of Windows.

WBF includes an IOCTL-based driver interface known as the Windows Biometric Driver Interface (WBDI) as well as a Windows service called the Windows Biometric Framework API (Windows) (WBS). WBS is also referred to as the WinBio service. WBDI drivers respond to requests from the WinBio service. WBF also includes Windows log-in support.

Overview of the Biometric technology.

To develop Biometric, you need these headers:

 * [winbio_ioctl.h](../winbio_ioctl/index.md)
 * [winbio_types.h](../winbio_types/index.md)

For the programming guide, see [Biometric](/windows-hardware/drivers/biometric).

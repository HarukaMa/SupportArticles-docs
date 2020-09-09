---
title: System error 1331 when you connect to a share
description: Helps fix the system error 1331 that occurs when you connect to a share.
ms.date: 09/08/2020
author: delhan
ms.author: Delead-Han
manager: dscontentpm
audience: itpro
ms.topic: troubleshooting
ms.prod: windows-server
localization_priority: medium
ms.reviewer: kaushika
ms.prod-support-area-path: Access to remote file shares (SMB or DFS Namespace)
ms.technology: Networking
---
# "Logon Failure: Account Currently Disabled" and "System Error 1331" Error Messages

This article provides a solution to the system error 1331 that occurs when you connect to a share.

_Original product version:_ &nbsp; Windows Server 2012 R2  
_Original KB number:_ &nbsp; 263936

## Symptoms

When you attempt to connect to a share, you may receive the following error message:
 **Share path/Name** is not accessible.
Logon failure: account currently disabled.
The computer may also display a "System error 1331" error message, which is the equivalent of the preceding "Logon failure: account currently disabled" error message.

> [!NOTE]
> There are no events logged in Event Viewer that are related to these errors.

## Cause

This problem can occur when you attempt to access a share that is located on a computer in a Windows 2000-based domain (either parent or child) from another Windows 2000-based domain, when you attempt to gain access to a share between a Windows NT 4.0-based domain and a Windows 2000-based domain with a two-way trust, or when you attempt to gain access to a share that is located in the same domain.

This problem occurs most commonly when a Windows NT 4.0-based or Windows 2000-based computer that has been a member of one domain is moved to another domain. The computer account for the computer that has been moved displays a red "X". For this problem to occur in a single-domain environment, the computer account had to have been set to disabled.

## Resolution

To resolve this problem, delete the disabled computer account in Active Directory Users and Computers.

## Status

Microsoft has confirmed that this is a problem in the Microsoft products that are listed at the beginning of this article.

## More information

The resolution in this article has also been documented to resolve the problem that causes the following error message:
Access is denied; account is currently disabled.
---
title: "Enabling Open in Desktop Setting by Group Policy"
ms.author: nwhite
author: nicholasswhite
manager: dougeby
audience: ITPro
ms.topic: reference
ms.service: o365-proplus-itpro
ms.localizationpriority: medium
ms.collection: Tier1
recommendations: false
description: "This article describes how tenant admins can enable the Open in Desktop feature using Group Policy."
ms.date: 01/24/2025
---

# Enabling Open in Desktop Setting by Group Policy

The Open in Desktop Group Policy setting allows tenant admins to configure Word, Excel, and PowerPoint file links hosted in OneDrive and SharePoint to open in desktop applications by default. This setting applies only to Windows users. It's particularly useful for tenants with compliance, policy, or usability requirements that necessitate opening files in desktop applications.

## User and policy interaction

When you enable this policy, file links in OneDrive and SharePoint open in desktop apps, such as Word, Excel, PowerPoint, and Outlook. The policy ensures that users automatically access files in the desktop environment.

To maintain control over their default file-opening behavior, users can set a different file-opening preference. This preference overrides the Group Policy that the tenant admin sets, even when the policy is in effect.

## Policy behavior

- **Enabled**: Files open in desktop applications (Word, Excel, PowerPoint, and Outlook) by default.
- **Disabled**: Files open in a web browser by default.
- **Not Configured**: The system determines the default behavior, typically opening files in a web browser.

> [!NOTE]
> This policy applies only to Microsoft 365 apps.

## Registry information

To manually configure this setting via the registry, use the following details:

- **Registry Hive**: `HKEY_CURRENT_USER`
- **Registry Path**: `software\policies\microsoft\office\16.0\common\internet`
- **Value Name**: `linksopenrightdefaultsettingisnative`
- **Value Type**: `REG_DWORD`
- **Enabled Value**: `1`
- **Disabled Value**: `0`

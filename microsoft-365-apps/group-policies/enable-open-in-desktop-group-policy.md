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
ms.date: 01/23/2024
---

# Enabling Open in Desktop Setting by Group Policy

This article describes how tenant admins can enable the Open in Desktop feature using Group Policy.

## Overview

The Open in Desktop Group Policy setting allows tenant admins to configure file links hosted in OneDrive and SharePoint (ODSP) to open in desktop applications by default. This setting is useful for tenants with compliance, policy, or usability requirements that necessitate opening files in desktop applications.

## Scope of the setting

The Open in Desktop Group Policy applies to file links hosted in ODSP and opened from Word, Excel, PowerPoint, and classic Outlook.

> [!NOTE]
> Support for opening files from Microsoft Teams is expected to be available in <month>.

## User and policy interaction

When you enable this policy, file links in ODSP open in desktop apps, such as Word, Excel, PowerPoint, and Outlook. The policy ensures that users automatically access files in the desktop environment.

To maintain control over their default file-opening behavior, users can set a different file-opening preference. This preference overrides the Group Policy that the tenant admin sets, even when the policy is in effect.

### SharePoint site admin policy interaction

This Group Policy setting applies to file links accessed from Word, Excel, PowerPoint, and Outlook apps. The SharePoint site admin policy is limited to file links accessed directly from the SharePoint site web page. To ensure that file links open in desktop apps, tenant admins must enable this Group Policy.

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

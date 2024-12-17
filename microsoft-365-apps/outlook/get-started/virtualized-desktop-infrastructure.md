---
title:  New Outlook for Windows for Virtualized Desktop Infrastructure (VDI)
ms.author: cpiranidesou
author: cpsou
manager: jhollander
audience: ITPro
ms.topic: overview
ms.service: outlook
ms.collection:
- Tier3
- virtualized-desktop-infrastructure.md
ms.localizationpriority: medium
ms.custom: intro-overview
recommendations: true
description: "Provides an overview of the new Outlook for Windows for VDI"
ms.date: 12/23/2024
---

# Upgrade to new Outlook for Windows for Virtualized Desktop Infrastructure (VDI)

This article describes the requirements and limitations of using the new Outlook for Windows in a virtualized environment.

## Requirements

|Requirement |Version|
|:-----|:-----|
|Windows|- Windows 10.0.17763.0 (1809) or higher </br>- Windows Server 2019 (10.0.17763) </br>- Windows Server 2022 (20348.2402) or higher</br>- Windows Server 2019 is NOT supported. Plan upgrades.</br>- Windows Server 2016 is NOT supported. Plan upgrades.|
|Webview2|Update to the most current version. Learn more: [Enterprise management of WebView2 Runtimes](/microsoft-edge/webview2/concepts/enterprise)|
|.NET Framework |4.7.2 or higher |

To prevent issues with starting the app, add the following processes to the exclusion list in the antivirus software that you’re using:
- olk.exe
- olkPushNotificationBackgroundTask.exe
- xpdAgent.exe
- relaunchNativeHost.exe

Alternatively, you can add the processes to the allowlist for programs in your DLP application. The method to accomplish this addition varies. For specific instructions, contact your DLP application’s manufacturer.

## Virtualization provider requirements

### Azure Virtual Desktop

The following minimum versions are necessary to support the new Outlook for Windows:

- Remote Desktop Client for Windows 1.2.2606
- Remote Desktop Client for Mac 10.7.7

Microsoft recommends using the latest available versions.

### Windows 365

The following minimum versions are necessary to support the new Outlook for Windows:

- Remote Desktop Client for Windows 1.2.2606
- Remote Desktop Client for Mac 10.7.7

Microsoft recommends using the latest available versions.

### Citrix Virtual Apps and Desktops and Citrix DaaS requirements

The following minimum versions are necessary to support the new Outlook for Windows:

Citrix Workspace app:

- Windows 2203 LTSR (and any CU)
- Windows 2302 CR

Citrix Virtual Delivery Agent (VDA):

- 2203 LTSR (and any CU)
- 2212 CR
- 1912 CU6 (but latest CU recommended - please note App Sharing is not supported on 1912)

### VMware Horizon and Workspace ONE requirements

The following minimum versions are necessary to support the new Outlook for Windows:

- Horizon 8 2111 ESB (8.4)

## Deploy the new Outlook for Windows

> [!NOTE]
> The new Outlook for Windows is installed as part of Windows for Germanium (24H2) and later builds.

See instructions to perform a machine-wide installation in [Deploy new Outlook](/microsoft-365-apps/outlook/get-started/deployment-new-outlook).
1.	Download the .exe installer.
2.	Distribute the installer to your target computers using Intune, Microsoft Endpoint Configuration Manager, Group Policy, or non-Microsoft distribution software.
3.	Run the installer on each computer.

## Troubleshooting Outlook for Windows deployment errors
See [Troubleshoot deployment issues in new Outlook](/microsoft-365-apps/outlook/troubleshoot/troubleshoot-deployment-new-outlook?tabs=windows11)

> [!NOTE]
> As mentioned in [Installation issues due to policy restrictions](/outlook/troubleshoot/troubleshoot-deployment-new-outlook?tabs=windows11#installation-issues-due-to-policy-restrictions),  if **AllowAllTrustedApps** is disabled, the new Outlook app installation fails. This issue has been fixed in the Windows October cumulative update KB5031455 for [Windows 11](https://support.microsoft.com/topic/october-31-2023-kb5031455-os-builds-22621-2506-and-22631-2506-preview-6513c5ec-c5a2-4aaf-97f5-44c13d29e0d4) and [Windows 10](https://support.microsoft.com/topic/october-26-2023-kb5031445-os-build-19045-3636-preview-03f350cb-57f9-45e6-bfd7-438895d3c7fa). If this optional October update isn't available for your OS build, the November security update will include the fix.

## Controlling updates for Outlook for Windows
See [Manage updates in new Outlook for Windows](/microsoft-365-apps/outlook/manage/manage-updates-new-outlook-windows)

## Disk Footprint – Key folders and location
> [!IMPORTANT]
> If you're using non-persistent VDI, [FSLogix](/fslogix/overview-what-is-fslogix) won't roam user data in the new Outlook for Windows.

### Install Location

The MSIX installer installs the new Outlook app in the WindowsApps folder. Because users can’t write to the WindowsApps folder, this location adds better protection against attacks that try to alter the installation of the Outlook app.

The name of the folder where the new Outlook app is installed is dynamic and it changes when the app’s version is updated. The folder name begins with **_Microsoft.OutlookForWindows__**, ends with **__8wekyb3d8bbwe_**, and includes the app’s version number and machine architecture in between. For example, **_Microsoft.OutlookForWindows_1.2024.717.400_x64_8wekyb3d8bbwe_**.

The current version install location can be found by running the following in powershell:
```Command Line
(get-appxpackage Microsoft.OutlookForWindows).InstallLocation
```

> [!NOTE]
> The MSIX installer and all files in the directory are signed with a Microsoft certificate.

### Profile and cache locations for the new Outlook for Windows

All user settings and configurations are stored in:

-	C:\Users\<username>\AppData\Local\Packages\Microsoft.OutlookForWindows_8wekyb3d8bbwe\
-	C:\Users\<username>\AppData\Local\Microsoft\olk\

## Folder Exclusions for Roaming

> [!IMPORTANT]
> If you're using non-persistent VDI, [FSLogix](/fslogix/overview-what-is-fslogix) won't roam user data in the new Outlook for Windows.

### Recommended for exclusion

|Folder                      |Folder path |Role |Exclusion impact |
|----------------------------|------------|---------|-----------------|
|**Logs and Telemetry cache**| %LocalAppData%/Microsoft/olk/logs</br>%LocalAppData%/Microsoft/olk/xpdApi.log</br>%LocalAppData%/Microsoft/olk/cache</br>%LocalAppData%/Microsoft/olk/feedback | Diagnostics, perf logs, update logs, and feedback items. | No impact. |
|**WebStorage**              | %LocalAppData%/Microsoft/Olk/EbWebView/default/WebStorage | Storage used and managed by the browser when accessing other web apps inside a web app using iframes. | Loading these apps again could be slower after clearing this cache. |
|**GPU Cache**               | %LocalAppData%/Microsoft/olk/EBWebView/default/GPUCache | GPU cache. | No impact. |

### Review tradeoff considerations, requiring evaluation and testing for these environments

|Folder                      |Folder path |Role |Exclusion impact |
|----------------------------|------------|---------|-----------------|
|**Service worker**             | %LocalAppData%/Microsoft/olk/EBWebView/default/Service Worker/CacheStorage</br>%LocalAppData%/Microsoft/olk/EBWebView/default/Code Cache | Code and caching of Web/JS Scripts for the app to run. | Reduced performance to download and load scripts on every app launch |
|**IndexedDB and Local Storage**| %LocalAppData%/Microsoft/olk/EBWebView/default/IndexedDB</br>%LocalAppData%\Microsoft\Olk\EBWebView\Default\Local Storage</br>%LocalAppData%/Microsoft/olk/Attachments| Holds app and user data and is the recommended way to cache data at scale in a web app to improve responsiveness. | -	User will need to sign in again if this data is not roamed.</br>-	Significantly higher app launch times as data needs to be downloaded and cached every time.</br>-	The size of the data varies based on the user profile.</br>|
|**Cache**                      | %LocalAppData%/Microsoft/olk/EBWebView/default/Cache | Cache used and managed by the browser for the contents of all network calls that leave the app. Also known as Disk Cache. | Images and other resources that are cached will need to be downloaded again. |

Other than the folders in this section, we don't recommend excluding additional directories.

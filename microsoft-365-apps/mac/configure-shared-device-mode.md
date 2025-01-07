---
title: "Configure shared device mode on iOS/iPadOS"
ms.author: chinmayjain
author: nicholasswhite
manager: dougeby
audience: ITPro
ms.topic: conceptual
ms.service: o365-proplus-itpro
ms.subservice: office-mac
ms.localizationpriority: medium
ms.collection: Tier3
recommendations: false
description: "Provides information to admins on how to set up and configure shared iOS device mode"
ms.date: 01/08/2025
---

# Configure shared device mode on iOS/iPadOS

This article provides guidance on setting up shared device mode for Microsoft 365 apps on iOS/iPadOS devices. Shared device mode enables multiple users to securely share the same device while accessing Microsoft 365 apps. The configuration process involves enrolling devices, assigning necessary applications, and applying a configuration policy to enable shared device mode.

### Prerequisites

Before configuring, ensure the following prerequisites are met:

- Devices are enrolled in Microsoft Intune.
- Users have valid Microsoft 365 accounts.
- The Microsoft Authenticator app is assigned to targeted devices.

Additionally, you must complete the *first five steps* and *prerequisites* outlined in [Set up enrollment for devices in shared device mode](/mem/intune/enrollment/automated-device-enrollment-shared-device-mode). These steps are critical for enabling shared device mode and include:

- Creating an Apple enrollment policy.
- Setting up a dynamic Microsoft Entra group.
- Creating an assignment filter.
- Configuring a single sign-on (SSO) app extension policy.
- Assigning the Microsoft Authenticator app.

## Assign Microsoft 365 apps and configure shared device mode

Follow these steps to enable shared device mode for Microsoft 365 apps on iOS/iPadOS devices:

### Assign Microsoft 365 apps to devices

1. Navigate to **Apps > iOS/iPadOS > Add** in the Microsoft Intune portal.
2. From the **App type** dropdown, select **iOS App Store**, then choose **Select**.
3. Use the **Search the App Store** link to locate the required Microsoft 365 apps such as Word, Excel, or PowerPoint, then choose **Select**.
4. Select **Next**.

### Assign to groups

Add the groups or devices for testing shared device mode.

1. Under **Available for enrolled devices**, select the group and choose **Next**.
2. Select **Create** to finalize app assignments.

### Configure app policies

1. Navigate to **Apps > App Configuration Policies > Add > Managed Device**.
2. Provide a name for the configuration policy (for example, "Shared Device Mode Policy").
3. Under **Platform**, select **iOS/iPadOS**.
4. Choose **Select app**, choose the associated app, and select **OK**.
5. Select **Next**.

### Set configuration values

1. In the **Settings** tab, under **Configuration settings format**, select **Use configuration designer**.

2. Add the following key-value pair:

   - **Configuration key**: shareddevicemodeenabled
   - **Value type**: Boolean
   - **Configuration value**: true

### Assign policies to groups

1. Select **Next**.
2. Under the **Assignments** tab, include the groups or devices for testing.
3. Proceed to the **Review + create** tab.
4. Verify all selections and select **Create** to finalize the configuration.

## Reporting bugs

If you encounter any issues while using Microsoft 365 apps in shared device mode, your feedback helps improve the experience. Use the [bug reporting form](https://forms.office.com/r/Xbqw3PFZHr) to submit feedback.


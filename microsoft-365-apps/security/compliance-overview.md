---
title: Compliance in Microsoft 365 Apps
author: nicholasswhite
ms.author: nwhite
manager: dougeby
audience: ITPro
ms.topic: conceptual
ms.service: o365-proplus-itpro
ms.collection: 
 - tier1
 - essentials-compliance
ms.localizationpriority: medium
description: Learn about compliance certifications, dependencies, and features in Microsoft 365 Apps supporting data protection and regulatory requirements.
ms.date: 11/20/2024
---

# Compliance in Microsoft 365 Apps

Microsoft 365 Apps provide built-in compliance features and support to help organizations meet national, regional, and industry-specific regulations. These apps align with Microsoft's commitment to data protection, privacy, and compliance, offering tools to help secure and manage data effectively.

## Shared responsibility model

Microsoft ensures that Microsoft 365 Apps comply with various industry standards and regulatory frameworks. However, customers are responsible for implementing their data protection and compliance strategies to align with their specific organizational requirements.

## Compliance certifications

Microsoft 365 Apps are covered under several compliance certifications and regulatory standards. The following table summarizes key certifications:

| Certification or Standard | Description | Applicability |
|---------------------------|-------------|---------------|
| GDPR                      | EU General Data Protection Regulation for data privacy | Global |
| ISO 27001                 | International standard for information security management | Global |
| HIPAA                     | U.S. Health Insurance Portability and Accountability Act | United States |
| SOC 2 Type 2              | Service Organization Controls for data security | Global |

For more certifications, visit [Microsoft Compliance Offerings](/compliance/regulatory/offering-home).

## Compliance dependencies

Microsoft 365 Apps uses other Microsoft services for compliance, including:

- [Microsoft Purview](/purview/purview): A suite of data governance and compliance tools.
- [Microsoft Entra ID](/entra/fundamentals/whatis): Identity and access management, formerly known as Azure Active Directory (Azure AD).
- [Microsoft Purview Compliance Manager](/purview/compliance-manager): Tools for managing compliance across your organization.
- [Microsoft Intune](/mem): Enables device compliance policies, conditional access, and other compliance features.

## Microsoft Intune capabilities for compliance

Microsoft Intune offers robust capabilities to strengthen your compliance posture within Microsoft 365 Apps:

- **Device Compliance Policies**: Set rules that devices must meet to be compliant, including requiring a minimum operating system version and enforcing password complexity. For more information, see [Device Compliance Policies](/mem/intune/protect/device-compliance-get-started).
- **Conditional Access**: Use device compliance status to control access to organizational resources, ensuring that only compliant devices can access sensitive data. For more information, see [Conditional Access](/mem/intune/protect/conditional-access).
- **Integration with Microsoft Purview**: Apply auditing and reporting features to monitor data usage and ensure adherence to compliance policies. For more information, see [Device Protection Features](/mem/intune/protect/device-protect).
- **Actions for Noncompliance**: Configure automatic actions for devices that fall out of compliance, such as sending notifications or restricting access. For more information, see [Actions for Noncompliance](/mem/intune/protect/actions-for-noncompliance).

These capabilities enhance compliance management by ensuring devices and data within your organization adhere to defined security and compliance policies.

## Data residency and protection

Microsoft 365 Apps ensure compliance with data residency requirements by supporting Microsoft Cloud's regional and global data storage policies. These policies include:

- **Data location**: Data is stored in Microsoft-managed data centers with Multi-Geo and Advanced Data Residency options.
- **Encryption**: Data is encrypted at rest and in transit.

For detailed information, see [Overview of Data Residency in Microsoft 365](/microsoft-365/enterprise/m365-dr-overview#overview-of-data-residency).

## Compliance features

Microsoft 365 Apps include several compliance features that help organizations meet regulatory requirements, manage data lifecycles, and protect sensitive information. These features are designed to ensure your organization can effectively monitor, classify, and safeguard its data while maintaining compliance with industry standards. The following sections highlight key compliance features available in Microsoft 365 Apps.

### Data lifecycle management

Microsoft 365 Apps support data lifecycle management through retention policies and labels. These features help organizations retain or delete data based on compliance requirements. For setup instructions, see [Retention policies and labels](/microsoft-365/compliance/retention).

### Auditing and reporting

Microsoft Purview supports auditing and reporting for Microsoft 365 Apps. IT administrators can monitor data usage and ensure adherence to organizational compliance policies. Features include:

- eDiscovery: Enables organizations to locate data for legal or regulatory needs.
- Data Retention Policies: Helps organizations manage data lifecycles.

For more information, visit the [Microsoft Purview compliance portal](/compliance).

### Privacy controls

Microsoft 365 Apps include privacy controls to manage data collection, storage, and sharing:

- Data Loss Prevention (DLP): Prevents sensitive information from being shared outside the organization.
- Sensitivity Labels: Enables classification and protection of documents and emails.

For details, see [Privacy controls in Microsoft 365 Apps](/deployoffice/privacy/overview-privacy-controls).

## Related articles

- [Microsoft Privacy Statement](https://privacy.microsoft.com/privacystatement)
- [Microsoft Trust Center](https://www.microsoft.com/trust-center)
- [Microsoft Compliance](/compliance)
- [Microsoft Purview compliance portal](https://compliance.microsoft.com)

---
title: "Monthly updates in portal capabilities for Dynamics 365 | MicrosoftDocs"
description: "Learn about what's new in the latest release of portal capabilities for Dynamics 365."
ms.custom: ""
ms.date: 09/28/2017
ms.service: crm-online
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: article
ms.assetid: 873dffa1-e598-4548-b494-7b67f2b01bb1
ms.reviewer: ""
author: sbmjais
ms.author: shjais
manager: sakudes
---
# What’s new in portal capabilities for [!INCLUDE[pn-dynamics-crm](../includes/pn-dynamics-crm.md)]

Welcome to portal capabilities for [!INCLUDE[pn-dynamics-crm](../includes/pn-dynamics-crm.md)]. Here's a list of features we added recently. For more information about the updates that have been made to portal capabilities for [!INCLUDE[pn-dynamics-crm](../includes/pn-dynamics-crm.md)] to date, along with additional details about those updates, see [portal capabilities for Microsoft Dynamics 365 Releases](https://support.microsoft.com/help/3181191/portal-capabilities-for-microsoft-dynamics-365-releases).

## Portal capabilities version 8.3 for Dynamics 365

Portal capabilities version 8.3 for Dynamics 365 has brought many new updates and features:
- **Ability to include attachments with knowledge articles**: You can display note attachments along with knowledge articles. To enable this feature, you create the site setting KnowledgeManagement/DisplayNotes and set the value to **true**. Portal users can also search for these attachments.

  > [!Note]
  > Search for attachments can only be performed on the note's description and file attachment name. The content of the attached file is not searchable.
  
- **Administrative wizard to add an entity to the portal**: This feature introduces a new administrative wizard to easily expose data on the portal. The entity created through the wizard takes the data from your organization and makes a subset of it available to your portal customers, based on the security and permission model you choose. 
- **Portal interaction tracking (preview)**: Use this preview feature to track a customer's interaction with your portal and funnel it to [!include[](../includes/pn-customerinsight-full.md)]. This will be helpful for plotting a 360-degree view of the user’s journey on your portal before and after a case is created. This also helps you to understand the real issue, avoid asking the user for the same information over again, and enable you to respond with relevant information.
- **Import metadata translation**: Use this feature to import the metadata translation of newly activated languages after you install a portal.
- **Source code availability for portals**: A one-time release of portal capabilities code is released to the Microsoft Download Center under MIT license for developers to download. This feature enables portals to be deployed to [!INCLUDE[pn-dynamics-crm](../includes/pn-dynamics-crm.md)] on-premises or online environments, and allows developers to customize the code to suit their specific business needs.
  > [!Note]
  > Source code is offered as a working sample and on an as-needed basis. No direct support will be provided for any modifications to the code.
- **Single sign-on (SSO) configuration improvements and support for Azure Active Directory B2C (Azure AD B2C)**: For portals that require a consumer-based sign-in, this feature now supports the ability to:
  - Configure your portal authentication to use SSO. 
  - Support Azure AD B2C for customer authentication.
  - Manage your portal security in Azure.
- **Support time zone&ndash;independent date formats in portals forms**: This feature adds support for **Date Only** and **Timezone Independent** behaviors for date/time fields.
- **Allowing non-global administrators to provision a portal**: You can now provision a portal if you are assigned to the System Administrator role of the CRM organization selected for the portal. You can now also manage an existing portal, if you have any of the following roles:
  - [!INCLUDE[pn-dynamics-crm](../includes/pn-dynamics-crm.md)] Service Administrator
  - System Administrator of the CRM organization selected for the portal
- **Store the custom domain name for a portal**: This feature stores the primary domain name of a portal on the website record. If the domain name is changed in the future, the latest primary domain name will be stored. 
- **Tracking cookie for portals**: A persistent cookie, Dynamics365PortalAnalytics, will be set whenever a user  goes to a portal. This cookie has an expiration of 90 days. This cookie does not store any of the user's personal data and is used by Microsoft to collect analytics about portal service. Please read the Microsoft online services privacy statement [here](https://go.microsoft.com/fwlink/p/?linkid=856855).
- **Performance improvement of header and footer on a portal**: Two new site settings, Header/OutputCache/Enabled and Footer/OutputCache/Enabled, are added to enable header/footer output caching when these settings are set to true. For new users, these site settings are set to true by default, thereby enabling header and footer output caching. For existing users who upgrade to a newer version of portal capabilities, output caching is disabled by default. It means that the Header and Footer web templates are parsed and rendered on every page load. To enable output caching, they must update the appropriate web templates and create the required site settings.

## December 2016 updates
The December 2016 update has brought many new features to the portal capabilities of [!INCLUDE[pn-dynamics-crm](../includes/pn-dynamics-crm.md)]. These updates allow for better interactions among companies, partners, and customers, and make the experience of navigating the portal faster and easier. Some of the major updates include:

- **Multiple language support:** Support customers from multiple regions by using a single portal.
- **East Asian language support:** Multiple-byte languages such as Japanese, Chinese, and Korean are now supported.
- **Faceted search:** New filters improve how quickly customers can find the content they are looking for while granting more control over visibility of content.
- **Product filtering:** Portal users can trim access to knowledge articles related to their product ownership to avoid information overload.
- **Content access levels:** A new level of ownership associated with a portal contact, account, or web role can be used to control access to knowledge articles, to help target the right article at the right audience and prevent irrelevant articles from surfacing.
- **Knowledge article reporting enhancement:** The portal tracks where a knowledge article was used in the portal.
- **Project Service Automation integration:** Provide access and visibility for active and closed projects across all stages of a project lifecycle to partners and customers. Team members, reviewers, and customers can view project status, quotes, order forums, and bookable resources on the portal with this solution.
- **Field Service integration:** Expose information about active agreements, assets, work orders, invoices, and support cases to partners and customers on the portal with this solution.
- **Partner onboarding:** Recruit new partners for better customer sales and service experiences. Potential partners can apply for partner status through the portal.

### Privacy notice

[!INCLUDE[cc-privacy-crm-portals-data-exposed](../includes/cc-privacy-crm-portals-data-exposed.md)]

For more information about additional [!INCLUDE[pn-azure-shortest](../includes/pn-azure-shortest.md)] service offerings, see the [[!INCLUDE[cc_privacy_note_azure_trust_center](../includes/cc_privacy_note_azure_trust_center.md)]](https://azure.microsoft.com/support/trust-center/).  
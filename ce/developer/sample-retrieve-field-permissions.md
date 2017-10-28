---
title: "Sample: Retrieve field permissions (Developer Guide for Dynamics 365 Customer Engagement) | MicrosoftDocs"
description: "The sample shows how to retrieve secured fields for a user according to the steps outlined in Field security entities."
ms.custom: ""
ms.date: 10/31/2017
ms.reviewer: ""
ms.service: "crm-online"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "samples"
applies_to: 
  - "Dynamics 365 (online)"
helpviewer_keywords: 
  - "field security entities sample, enabling"
  - "enabling field security, sample"
ms.assetid: acb20fc8-4b62-4e92-b105-7d832c56d007
caps.latest.revision: 20
author: "JimDaly"
ms.author: "jdaly"
manager: "jdaly"
---
# Sample: Retrieve field permissions
This sample code is for [!INCLUDE[pn_dynamics_crm_online](../includes/pn-dynamics-crm-online.md)]. Download the complete sample here [Sample: Retrieve field permissions](https://code.msdn.microsoft.com/Sample-Retrieve-field-e5a31f0f). 

## Prerequisites
[!INCLUDE[sdk-prerequisite](../includes/sdk-prerequisite.md)]
  
## Requirements  
[!INCLUDE[sdk_SeeConnectionHelper](../includes/sdk-seeconnectionhelper.md)]
  
## Demonstrates  
 This sample shows how to retrieve secured fields for a user according to the steps outlined in [Field security entities](field-security-entities.md).  
  
## Example  
 [!code-csharp[FieldSecurity#RetrieveSecuredFieldsForAUser1](../snippets/csharp/CRMV8/fieldsecurity/cs/retrievesecuredfieldsforauser1.cs#retrievesecuredfieldsforauser1)]  
  
### See also  
 [How Field Security Can Be Used to Control Access to Field Values In Dynamics 365](security-dev/use-field-security-control-access-field-values.md)   
 [Field Security Entities](field-security-entities.md)   
<xref:Microsoft.Xrm.Sdk.IOrganizationService>
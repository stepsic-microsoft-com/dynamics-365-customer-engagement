---
title: "Discover the URL for your organization using the Web API (Developer Guide for Dynamics 365 Customer Engagement)| MicrosoftDocs"
description: "Learn how you can use the Web API to discover at runtime the organizations, or instances that the logged-on user belongs to"
ms.custom: ""
ms.date: 10/31/2017
ms.reviewer: ""
ms.service: "crm-online"
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
applies_to: 
  - "Dynamics 365 (online)"
ms.assetid: 2db13b4e-0e7c-4f25-b7be-70a612fb96e2
caps.latest.revision: 18
author: "JimDaly"
ms.author: "jdaly"
manager: "amyla"
---
# Discover the URL for your organization using the Web API

[!INCLUDE[](../../includes/cc_applies_to_update_9_0_0.md)]

The Discovery service for the [!INCLUDE[pn_dynamics_crm](../../includes/pn-dynamics-crm.md)] Customer Engagement Web API enables your applications to determine at run-time the organizations, also known as *instances*, that the logged-on user belongs to.  You can retrieve detailed information about those instances like the instance service URL, the [!INCLUDE[pn_crm_shortest](../../includes/pn-crm-shortest.md)] release version, the instance ID and more. You can use standard `$filter` and `$select` parameters to a Web API service request to customize the  returned list of instance data. The Discovery service is supported by all [!INCLUDE[pn_crm_shortest](../../includes/pn-crm-shortest.md)] deployment types: Online, on-premises, and IFD.  
  
 Clients applications may need access to a [!INCLUDE[pn_crm_shortest](../../includes/pn-crm-shortest.md)] instance where the instance URL may change over time.  For example, when a [!INCLUDE[pn_crm_shortest](../../includes/pn-crm-shortest.md)] instance is moved from one [!INCLUDE[pn_CRM_Online](../../includes/pn-crm-online.md)] datacenter to another. The Discovery service allows clients instance to persist the instance ID or instance unique name and then use the Discovery service to look-up the current instance access URL.  
  
 In addition to datacenter specific Discovery services, that are available on the 2011 (SOAP) endpoint and through the Web API, there is also a Web API only global Discovery service that spans all operational datacenters. For more information about the Discovery service on the 2011 endpoint see [Discover the URL for your organization using the Organization Service](../org-service/discover-url-organization-organization-service.md).  
  
## Information provided by the Discovery service  
 Organization information is stored in the `Instance` entity of the Discovery service.  To see the kind of information contained in that entity, send an HTTP GET request to the service for one of your instances.  
  
```http  
GET https://globaldisco.crm.dynamics.com/api/discovery/v1.0/Instances(UniqueName='myorg')  
```  
  
 In the above example, the global Discovery service of [!INCLUDE[pn_CRM_Online](../../includes/pn-crm-online.md)] is used to obtain the organization information of the instance with a unique name of "myorg". More details about this request is expanded upon later in this topic.  
  
### Scope of the returned information  
 For the global Discovery service, the `Instances` entity set, returns the set of instances that the user has access to across all geographies, when no filters are applied.   The returned data has a scope as described below.  
  
-   Includes all instances in the commercial cloud where the user is provisioned and enabled, except sovereign clouds instances are not returned  
  
-   Does not  include instances where the user's account is disabled  
  
-   Does not include instances where users have been filtered out based on an instance security group  
  
-   Does not include instances where the user has access as a result of being a delegated administrator  
  
-   If the calling user has access to no instances, the response simply returns an empty list  
  
## How to access the Discovery services  
 In general, the Web API address of the Discovery service has the following format: `<service base address>/api/discovery/`.  The addresses for  each deployment type are identified below. You can easily  find the Web API addresses and version number for your deployment in the [!INCLUDE[pn_crm_shortest](../../includes/pn-crm-shortest.md)] web application by navigating to **Settings > Customization > Developer Resources**  
  
### [!INCLUDE[pn_dynamics_crm_online](../../includes/pn-dynamics-crm-online.md)] Discovery services  
 The service base address of the global Discovery service is : `https://globaldisco.crm.dynamics.com/`. This results in the service address of `https://globaldisco.crm.dynamics.com/api/discovery/`.  
  
 The service base address of the Discovery service for a datacenter is : `https://disco.crm[N].dynamics.com/`. This results in the Discovery service address of `https://disco.crm[N].dynamics.com/api/discovery/`. Each datacenter has an N number associated with it. For a complete list of available [!INCLUDE[pn_CRM_Online](../../includes/pn-crm-online.md)] datacenters, and their N numbers,  see [Download endpoints using Developer resources page](../developer-resources-page.md).  
  
### On-premises and IFD Discovery service  
 [!INCLUDE[cc_sdk_onpremises_note](../../includes/cc-sdk-onpremises-note.md)] The service base address of the Discovery service for an on-premises or IFD deployment is : `http[s]://{servername}/` or `http[s]://dev.{servername}/`. This results in the service address of `http[s]://{servername}/api/discovery/` or `http[s]://dev.{servername}/api/discovery/`.  
  
## Using the Discovery service  
 An entity set named `Instances` is used to obtain instance information. You can use `$select` and `$filter` with the Instances entity set to filter the returned data. You can also use `$metadata` to obtain the metadata document of the service.  
  
### Authentication  
 [!INCLUDE[pn_CRM_Online](../../includes/pn-crm-online.md)] Web API instances of the Discovery service require authentication with OAuth access tokens. On-premise or IFD instances of the Discovery Web API adopt the authentication model of their deployment, supporting either Integrated Windows Authentication (IWA) or OAuth tokens from a trusted token provider. Web Application Session authentication is not supported.  
  
 When the Discovery service is configured for OAuth authentication, a request sent  to the service Web API without an access token triggers a bearer challenge with the authority of the “common” endpoint and the resource ID of the service.  Similarly, when an on-premise deployment is configured for OAuth, a bearer challenge returns the on-premise authority URL and the resource ID of the service.  
  
### Web API versioning  
 Versioning of the Discovery service for a datacenter or on-premises/IFD is supported and is consistent with version numbering as used by the Organization service . However, the global Discovery service of [!INCLUDE[pn_CRM_Online](../../includes/pn-crm-online.md)] is not tied to the version number of the [!INCLUDE[pn_crm_shortest](../../includes/pn-crm-shortest.md)] deployment. Instead, the global service uses its own version numbering. As of this writing, the global Discovery service of [!INCLUDE[pn_CRM_Online](../../includes/pn-crm-online.md)] is at version 1.0 (v1.0). For example:  
  
```http  
GET https://globaldisco.crm.dynamics.com/api/discovery/v1.0/Instances(UniqueName='myorg')  
```  
  
### CORS support  
 The Discovery service Web API supports the CORS standard for cross-origin access as does the Web API.  For more information about CORS support see [Use OAuth with Cross-Origin Resource Sharing  to connect a Single Page Application  to Dynamics 365](../oauth-cross-origin-resource-sharing-connect-single-page-application.md).  
  
### Examples  
  
-   Get the details of a specific instance. If you leave out the GUID, all instances that the authenticated user has access to are returned.  
  
    ```http  
    GET https://disco.crm.dynamics.com/api/discovery/v8.1/Instances(<guid>)  
    GET https://dev.crm.external.contoso.com/api/discovery/v8.1/Instances(<guid>)  
    ```  
  
-   You can use the UniqueName attribute as an alternate key.  
  
    ```http  
    GET https://globaldisco.crm.dynamics.com/api/discovery/v1.0/Instances(UniqueName='myorg')  
    ```  
  
-   Retrieve a list of available instances, filtered by production type.  
  
    ```http  
    GET https://globaldisco.crm.dynamics.com/api/discovery/v1.0/Instances?$select=DisplayName,Description&$filter=Type+eq+0   
    ```  
  
-   Retrieve a specific instance's ID property value.  
  
    ```http  
    GET https://disco.crm.dynamics.com/api/discovery/v8.1/Instances(UniqueName='myorg')/Id/$value  
    ```

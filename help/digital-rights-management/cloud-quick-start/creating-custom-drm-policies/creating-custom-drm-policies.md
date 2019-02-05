---
seo-title: Create custom DRM policies (Optional)
title: Create custom DRM policies (Optional)
uuid: 701b51d9-6dde-4c21-bc5b-09e612582968
---

# Create custom DRM policies (Optional){#create-custom-drm-policies-optional}

The Primetime Cloud DRM Protection Kit comes with a few pre-configured policies that can be used during packaging. If additional policy configurations are desired, for example, a specific SWF-Whitelisting right, the included Primetime DRM Policy Manager can be used to generate custom policies.

>[!NOTE]
>
>All policies must use ANONYMOUS authentication (not Username Password or Custom) - regardless of whether or not the Custom Auth/Entitlement workflow is used.

Included with the  Policy Manager is the [!DNL flashaccesstools.properties] configuration file, which has been modified to expose only the configurable policy options that  Primetime Cloud DRM  Service supports. Setting policy options that are not supported by the  Primetime Cloud DRM  Service will result in license acquisition errors. For information on using the Primetime DRM Policy Manager, refer to: [Primetime DRM Reference Implementations: Policy Manager](https://help.adobe.com/en_US/primetime/drm/5.3/reference_implementations/index.html#concept-DRM_Policy_Manager).

To create a new policy, update the [!DNL flashaccesstools.properties] file as desired, and then use the command:

```
java -jar libs/AdobePolicyManager.jar new myPolicy.pol
```


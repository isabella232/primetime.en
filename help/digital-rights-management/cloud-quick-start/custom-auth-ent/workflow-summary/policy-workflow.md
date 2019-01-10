---
seo-title: Policy workflow details
title: Policy workflow details
uuid: b355fcf6-3416-440f-9b30-a155e20f9f74
index: y
internal: n
snippet: y
---

# Policy workflow details{#policy-workflow-details}

When Primetime Cloud DRM processes a license request, it parses the DRM policy in the request to determine if a call to a backend-entitlement service is required before the content can be shown. If a BEES call *is* required,  Primetime Cloud DRM will create the BEES request, then parse the DRM policy to obtain a specified BEES URL endpoint for the BEES request. 

1. Apply your DRM policy that indicates the BEES requirement, specifying the following two custom properties in the policy:

    * `policy.customProp.1=bees.required=<true | false>` 
    * `policy.customProp.2=bees.url=<url to your BEES endpoint>`

<a id="example_F617FC49A4824C0CB234C92E57D876D3"></a>

For example, using the  Primetime DRM Policy Manager ( [!DNL AdobePolicyManager.jar]), you would specify the following two custom properties in the [!DNL flashaccesstools.properties] configuration file:

* `policy.customProp.1=bees.required=true` 
* `policy.customProp.2=bees.url=https://mybeesserver.example.com/bees`

>[!NOTE]
>
>If you are already using `policy.customProp.1` or `policy.customProp.2` for another property, simply use unique numbers for the newer properties.


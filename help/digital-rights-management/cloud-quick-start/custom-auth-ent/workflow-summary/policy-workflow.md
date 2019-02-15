---
seo-title: Policy workflow details
title: Policy workflow details
uuid: b355fcf6-3416-440f-9b30-a155e20f9f74
---

# Workflow summary{#workflow-summary}

* **Policy** - Create a DRM BEES-aware policy that indicates BEES is required for all content packaged using thispolicy.
* **Packaging** - Package content using the BEES-aware DRM policy.
* **Authentication** - Authenticate your client device and use the Primetime DRM API, or the Primetime API, toassociate this token with Primetime Cloud DRM. Doing this will cause the client device to send this authenticationtoken up to Primetime Cloud DRM along with all license requests. Primetime Cloud DRM will not process thistoken, but instead will pass it along (as an opaque blob) to your BEES endpoint for processing.
* **Licensing** - Request a license for your protected content. The client device will automatically append yourpreviously-set authentication token to the call.
* **Entitlement** - Primetime Cloud DRM will determine that the content was packaged with a policy that requiresBEES. Primetime Cloud DRM will construct a JSON request to send to the BEES endpoint. The BEES responsewill instruct Primetime Cloud DRM on whether or not to issue a license, and optionally, which DRM policy to use.

# Policy workflow details{#policy-workflow-details}

When Primetime Cloud DRM processes a license request, it parses the DRM policy in the request to determine if a call to a backend-entitlement service is required before the content can be shown. If a BEES call *is* required,  Primetime Cloud DRM will create the BEES request, then parse the DRM policy to obtain a specified BEES URL endpoint for the BEES request. 

1. Apply your DRM policy that indicates the BEES requirement, specifying the following two custom properties in the policy:

    * `policy.customProp.1=bees.required=<true | false>` 
    * `policy.customProp.2=bees.url=<url to your BEES endpoint>`

<!--<a id="example_F617FC49A4824C0CB234C92E57D876D3"></a>-->

For example, using the  Primetime DRM Policy Manager ( [!DNL AdobePolicyManager.jar]), you would specify the following two custom properties in the [!DNL flashaccesstools.properties] configuration file:

* `policy.customProp.1=bees.required=true` 
* `policy.customProp.2=bees.url=https://mybeesserver.example.com/bees`

>[!NOTE]
>
>If you are already using `policy.customProp.1` or `policy.customProp.2` for another property, simply use unique numbers for the newer properties.


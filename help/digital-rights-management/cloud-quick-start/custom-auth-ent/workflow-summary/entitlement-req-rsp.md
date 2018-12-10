---
description: null
seo-description: null
seo-title: Entitlement request and response details
title: Entitlement request and response details
uuid: 75dcc3f6-3283-47b7-85af-45b52da2ede1
index: y
internal: n
snippet: y
---

# Entitlement request and response details{#entitlement-request-and-response-details}

When  Primetime Cloud DRM determines that content was packaged with a BEES-aware DRM policy, it constructs the following JSON request to send to the BEES endpoint specified in the DRM policy:

```
{
    "title":"Entitlement Request",
    "type":"object",
    "properties": {
        "messageID": {
            "type":"string",
            "description":"Unique ID for this message. Used to confirm that the
                           returned response is for this particular message."
        },
        "version": {
            "type":"string",
            "description":"BEES Request Version. Currently 1."
        },
        "contentID": {
            "type":"string",
            "description":"Content ID (GUID)"
        },
        "customerSpecificAuthToken": {
            "type":"string",
            "description":"Base64-encoded authentication token. Must be set
                           explicitly by client before making the license request."
        }
    },
    "required": [
        "messageID",
        "version",
        "contentID"
    ]
}

```

The following response is expected from the BEES endpoint:

```
{
    "title":"Entitlement Response",
    "type":"object",
    "properties": {
        "messageID": {
            "type":"string",
            "description":"ID of the Entitlement Request that this Response is
                           handling. Must exactly match the ID of the request
                           or this response will be rejected."
        },
        "version": {
            "type":"string",
            "description":"BEES Response Version. Currently 1."
        },
        "isAllowed": {
            "type":"boolean",
            "description":"Grant the license or not."
        },
        "policy": {
            "type":"string",
            "description":"Base64-encoded policy to enforce  If no policy is
                           provided, the policy that was packaged with the content
                           during packaging time will be used to generate the license."
        },
        "error": {
            "type":"integer",
            "description":"An error number produced by the entitlement server.
                           Will be passed to the client as the 'code' field of
                           the server error response."
        },
        "errorText": {
            "type":"string",
            "description":"Additional error information produced by the
                           entitlement server. Will be passed to the client as
                           the 'text' field of the server error response."
        }
    },
    "required": [
        "messageID",
        "version",
        "isAllowed"
    ]
}

```

Primetime Cloud DRM uses the response to determine whether or not it should issue a license to the requesting device, and if it should substitute a new DRM policy into the license generation process. If `isAllowed` is `true` and no policy is provided in the response, then the original DRM Policy used during content packaging time will be used to generate the license. 

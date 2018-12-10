---
seo-title: License request error handling
title: License request error handling
uuid: 9a55c4ad-65c1-4e99-a93f-06c28c2f2a8e
index: y
internal: n
snippet: y
---

# License request error handling{#license-request-error-handling}

If an error occurs during request parsing, a `HandlerParsingException` occurs. This exception includes error information that is returned to the client. If you need to retrieve the error information, you need to call `HandlerParsingException.getErrorData()`. If an error occurs during the generation of a license because of DRM policy requirements that have not been satisfied, a `PolicyEvaluationException` occurs. This exception also includes `ErrorData` to be returned to the client.

See the API documentation for `LicenseRequestMessage.generateLicense()` for details on how DRM policies are evaluated during license generation. 

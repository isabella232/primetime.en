---
seo-title: Prerequisites
title: Prerequisites
uuid: 5c85ce72-28a9-45d8-b951-46a697e362ea
index: y
internal: n
snippet: y
---

# Prerequisites{#prerequisites}

Before packaging content, a Primetime DRM Packager certificate is required. It must be requested via the Primetime DRM Certificate Enrollment Process. Only a packager certificate is required (no License Server or Transport). Please indicate in the Certificate Request email that the request is for a certificate to use with the DRM Service.

[https://help.adobe.com/en_US/primetime/drm/5.3/drm_certificate_enrollment.pdf](https://help.adobe.com/en_US/primetime/drm/5.3/drm_certificate_enrollment.pdf)

There are two levels of packaging certificates - PRODUCTION and TRIAL. Content that is packaged using TRIAL certificates is for development use only and will not play after the certificate expires. All licenses issued to TRIAL content will have a maximum hard-coded policy expiration date equal to that of the expiration date of the certificate (if not set in the DRM policy). 

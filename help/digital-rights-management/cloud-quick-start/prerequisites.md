---
seo-title: Prerequisites
title: Prerequisites
uuid: 5c85ce72-28a9-45d8-b951-46a697e362ea
---

# Prerequisites {#prerequisites}

Before packaging content, a Primetime DRM Packager certificate is required. It must be requested via the Primetime DRM Certificate Enrollment Process. Only a packager certificate is required (no License Server or Transport). Please indicate in the Certificate Request email that the request is for a certificate to use with the DRM Service.

[Certificate Enrollment Guide](../../digital-rights-management/certificate-enrollment-guide/title-page/about-certs.md)

There are two levels of packaging certificates - PRODUCTION and TRIAL. Content that is packaged using TRIAL certificates is for development use only and will not play after the certificate expires. All licenses issued to TRIAL content will have a maximum hard-coded policy expiration date equal to that of the expiration date of the certificate (if not set in the DRM policy). 

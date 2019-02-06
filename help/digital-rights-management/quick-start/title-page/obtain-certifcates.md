---
description: null
seo-description: null
seo-title: Obtain Certificates
title: Obtain Certificates
uuid: dd01931b-289e-4876-9344-dd90c3c8c162
---

# Obtain Certificates{#obtain-certificates}

After the SDK software is delivered, the designated Company Certificate Administrator will receive an invitation to complete the Adobe Primetime DRM Certificate Enrollment registration process. For more information, see the *Primetime DRM Certificate Enrollment Guide*. 

1. The Administrator appoints at least one individual to act as the Certificate Requester.
1. The Certificate Requester generates a private key and a CSR.
1. The Requester submits a certificate request.
1. The Company Administrator approves the request.
1. The Adobe Certificate Administrator confirms the submission.
1. The Requester receives the certificate, binds the certificate with the private key, and deploys the cerfiticate. as described in .

   For more information about deploying the certificate, see the *Deploying the Adobe Primetime DRM Server for Protected Streaming* guide.
1. Steps 3 through 6 must be completed for each certificate type.

   For the Primetime DRM Production version, the Requester must make separate requests for the License Server, Packaging, and Transport certificates, which are valid for two years.

   Customers that use the Primetime DRM Evaluation or Trial versions only need one certificate that is valid for 1 year / 90 days, respectively. 


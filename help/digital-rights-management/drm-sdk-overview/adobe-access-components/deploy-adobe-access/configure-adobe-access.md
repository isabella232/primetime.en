---
seo-title: Configure Adobe Primetime DRM
title: Configure Adobe Primetime DRM
uuid: c14c2792-d207-4f39-b856-610520bdaa28
index: y
internal: n
snippet: y
---

# Configure Adobe Primetime DRM{#configure-adobe-primetime-drm}

A key advantage to Adobe Primetime DRM SDK is that you can install it on any Java™ application server or servlet container, such as Tomcat. You also need JDK™ 1.5 or higher. For more information on software requirements, see Primetime DRM SDK platform requirements: [http://www.adobe.com/products/flashaccess/systemreqs/](http://www.adobe.com/products/flashaccess/systemreqs/).

The high-level steps to deploy Primetime DRM are:

1. Install and configure Primetime DRM SDK. 
1. Obtain digital certificates from Adobe. 
1. Create a License Server using the SDK, or deploy Primetime DRM Server for Protected Streaming. 
1. Create content packaging and policy management tools to package content, use the provided content preparation tools, or license one of the Adobe HTTP Dynamic Streaming packagers. 
1. Define usage rules for your content, and create policies in support of those rules. 
1. Package your content using the packaging and policy management tools. 
1. Develop video applications with which consumers can view your protected content using Flash Player or Adobe AIR, or use an established OVP (Online Video Platform) that supports Primetime DRM. 
1. Deploy a SWF file for use with Flash Player to your website, or post the Adobe AIR installer for download.

These steps are expanded upon in the following sections, with references to other documents containing additional information. 

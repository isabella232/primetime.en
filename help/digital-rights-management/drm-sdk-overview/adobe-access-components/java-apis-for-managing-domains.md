---
description: These APIs are used to allow the server to handle client requests for joining and leaving device group domains.
seo-description: These APIs are used to allow the server to handle client requests for joining and leaving device group domains.
seo-title: Java APIs for managing device group domains
title: Java APIs for managing device group domains
uuid: 952772ea-502b-4ba9-8bcf-cd3562d9f633
---

# Java APIs for managing device group domains{#java-apis-for-managing-device-group-domains}

These APIs are used to allow the server to handle client requests for joining and leaving device group domains.

A device group domain is a logical collection of devices that are able to share licenses between each other. In order for this to happen, each device must first join/register to the same domain. The Primetime DRM SDK, running on a server, must handle the Device Domain join (register) requests, as well as Device Domain leave (de-register) requests. Devices that are not joined to any domain will be issued licenses that are bound to that device, which cannot be shared to any other device. 

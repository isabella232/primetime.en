---
seo-title: Register a device
title: Register a device
uuid: e1bad373-f19b-432b-b815-f686dbabd0ee
---

# Register a device{#register-a-device}

Let us assume that you have performed the following tasks:

* You have set up the Primetime DRM Server SDK. 
* You have set up an HTTP server for issuing pre-generated licenses. 
* You have created a Primetime application to view the protected content.

 The device registration phase involves the following actions: 

1. The application creates a randomly generated ID.
1. The application invokes the `DRMManager.authenticate()` method. The application must include the randomly generated ID in the authentication request. For instance, include the ID in the username field.
1. The action mentioned in Step 2 will result in Primetime DRM sending an authentication request to the customer's server. This request includes the device certificate:
   1. The server extracts the device certificate and the generated ID from the request and stores.
   1. The customer sub-system pre-generates licenses for this device certificate, stores them and grants access to them  in a way that associates them with the generated ID. .
1. The server responds to the request with a "success" message.
1. The application stores the generated ID.
>After the device registration, the application uses the generated ID in the same way as it would have used the device ID in the previous scheme: &nbsp; >
>1. The application will try to locate the generated ID. 
>1. If the generated ID is found, the application will use the generated ID while downloading the pre-generated licenses. The application will send the licenses to the Primetime DRM client for consumption using the `DRMManager.storeVoucher()` method. . 
>1. If the generated ID is not found, the application will go through the device registration procedure. 
>

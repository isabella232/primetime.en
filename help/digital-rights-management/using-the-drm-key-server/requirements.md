---
seo-title: Requirements for using Primetime DRM Key Server
title: Requirements for using Primetime DRM Key Server
uuid: 98a5b97e-e9b6-4489-9c5e-c997eb2f732e
index: y
internal: n
snippet: y
---

# Requirements for using Primetime DRM Key Server{#requirements-for-using-primetime-drm-key-server}

Primetime DRM Key Server is a multi-tenant Key Server for Remote iOS and / or Xbox 360 key delivery. If Remote Key Delivery is enabled in a policy for iOS, a Primetime DRM Key Server must be deployed in order to enable content playback on iOS clients. Primetime DRM Key Server is always required for Xbox 360. The minimum requirements for using Primetime DRM Key Server are:

* [Java JRE 1.6](http://www.oracle.com/technetwork/java/javase/downloads/index.html) or later. (In order to use HSM on Windows 64 bit, JRE 8 is required) 

  >[!NOTE]
  >
  >64-bit PKCS11 is now supported in OpenJDK 8: [http://openjdk.java.net/jeps/131](http://openjdk.java.net/jeps/131), and Oracle JDK: [http://bugs.java.com/bugdatabase/view_bug.do?bug_id=6880559](http://bugs.java.com/bugdatabase/view_bug.do?bug_id=6880559).

* [Apache Tomcat 7](http://tomcat.apache.org) 
* Credentials issued by Adobe 
* Credentials issued by Microsoft (for Xbox 360 clients)


---
description: To upgrade a server running Adobe Access Server for Protected Streaming, replace the flashaccessserver.war file deployed on your application server with the file included with the latest Adobe Access. If you wish to use the new configuration options described above, update your server’s flashaccess-tenant.xml. You also need to update jsafe.dll or libjsafe.so to the version included with the latest Adobe Access.
seo-description: To upgrade a server running Adobe Access Server for Protected Streaming, replace the flashaccessserver.war file deployed on your application server with the file included with the latest Adobe Access. If you wish to use the new configuration options described above, update your server’s flashaccess-tenant.xml. You also need to update jsafe.dll or libjsafe.so to the version included with the latest Adobe Access.
seo-title: Running the Adobe Access Server for Protected Streaming
title: Running the Adobe Access Server for Protected Streaming
uuid: c05c23d3-f6ba-4dd4-ae6a-9854b1cbb86f
index: y
internal: n
snippet: y
---

# Running the Adobe Access Server for Protected Streaming{#running-the-adobe-access-server-for-protected-streaming}

To upgrade a server running Adobe Access Server for Protected Streaming, replace the flashaccessserver.war file deployed on your application server with the file included with the latest Adobe Access. If you wish to use the new configuration options described above, update your server’s flashaccess-tenant.xml. You also need to update jsafe.dll or libjsafe.so to the version included with the latest Adobe Access.

Before running the Adobe Access Server for Protected Streaming, Adobe recommends that you verify that the configuration files are valid by using the utilities provided with the license server. For more details, see " [Configuration Validator](c_xgep_configuration-validator.md)".

To start Tomcat and the license server, run "catalina.bat start" or "catalina.sh start" from Tomcat's bin directory.

After the server has started, verify that it is configured properly by opening *http://license-server-host:port*/flashaccessserver/*tenant-name*/flashaccess/license/v1 in a browser window. If the tenant configuration was successfully loaded, a confirmation message is displayed. 

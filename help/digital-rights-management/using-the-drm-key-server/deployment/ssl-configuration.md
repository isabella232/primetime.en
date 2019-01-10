---
seo-title: SSL configuration
title: SSL configuration
uuid: 22aece56-7c88-4f72-bf75-81a3c64781fe
index: y
internal: n
snippet: y
---

# SSL configuration{#ssl-configuration}

SSL is required for Remote HTTPS key delivery. The SSL connections could be handled by the application server (i.e., by configuring SSL in Tomcat) or could be handled at another server (i.e., a Load balancer, SSL accelerator, or Apache). Remote HTTPS key delivery requires an SSL connection. The server needs an SSL certificate issued by a trusted CA.

There are a variety of options for configuring SSL. Below are examples for configuring SSL with client authentication in Apache and Tomcat.

The following example shows the Apache SSL configuration: 

```
SSLEngineon 
SSLCertificateFile "certs/server_cert.pem" 
SSLCertificateKeyFile "certs/server_key.pem" 
SSLOptions +StdEnvVars +FakeBasicAuth -ExportCertData +StrictRequire 
SSLRequireSSL 
ProxyRequests Off 
ProxyPass /http://keyserver-name:port/ 
ProxyPassReverse /http://keyserver-name:port/
```

The following example shows the Tomcat SSL configuration. To generate certificate and key files: 

```
Generate key:  
 openssl genrsa -des3 -out server.key 1024 
Generate CSR: 
 openssl req -new -key server.key -out server.csr 
Generate Certificate: 
 openssl x509 -req -days 365 -in server.csr -signkey server.key -out server.cer
```

When prompted for the common name, use your server’s Fully Qualified Domain Name (FQDN).

Copy [!DNL server.cer], and [!DNL server.key] to the Tomcat directory. Specify the following Connector in [!DNL conf/server.xml]: 

```
<Connector port="8443" protocol="HTTP/1.1" SSLEnabled="true" 
 maxThreads="150" scheme="https" secure="true" 
 sslProtocol="TLS" 
 SSLCertificateFile="${catalina.base}/server.cer" 
 SSLCertificateKeyFile="${catalina.base}/server.key" 
 SSLPassword="password-for-key-file" 
 SSLVerifyClient="require"/>
```


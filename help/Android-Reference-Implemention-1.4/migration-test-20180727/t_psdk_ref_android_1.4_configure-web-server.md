---
description: null
seo-description: null
seo-title: Configure the web server to debug and run builds
title: Configure the web server to debug and run builds
uuid: 8b2f33d7-83ff-4169-a27b-21e8e01112f5
index: n
internal: n
snippet: y
translate: y
---

# Configure the web server to debug and run builds

Adobe Flash Player requires an authorization token to enable advanced features required by the Primetime reference implementation. The Primetime reference implementation loads this token at runtime. Request a Flash Player authorization token from your Adobe Enablement Representative for your web server domain. For example, if your domain is www.yourhost.com, the token is hashed to www.yourhost.com.

>1. Download and install a web server of your choice, for example [Apache's HTTP Server](http://httpd.apache.org/download.cgi) or [Nginx](http://wiki.nginx.org/Install).
>1. Under the root directory for your web server, create two directories:
>    
>    * `pmp-desktop`: this is where you configure the project output files.
>    * `pmp-desktop/token`: this is where you add the Flash Player authorization token.
>    
>1. Place the Flash Player authorization token you received from your Adobe Enablement Representative in the `token` directory.
>1. Rename the token to `token.dat`.
>1. Verify the token is accessible from `http://www.yourhost.com/pmp-desktop/token/token.dat`, where `www.yourhost.com` is your domain.

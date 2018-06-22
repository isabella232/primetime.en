---
description: 
seo-description: 
seo-title: Configure the web server to debug and run builds
title: Configure the web server to debug and run builds
---

# Configure the web server to debug and run builds

Adobe Flash Player requires an authorization token to enable advanced features required by the Primetime reference implementation. The Primetime reference implementation loads this token at runtime. Request a Flash Player authorization token from your Adobe Enablement Representative for your web server domain. For example, if your domain is www.yourhost.com, the token is hashed to www.yourhost.com.

>1. Download and install a web server of your choice, for example [Apache's HTTP Server](http://httpd.apache.org/download.cgi) or [Nginx](http://wiki.nginx.org/Install).
>   
>1. Under the root directory for your web server, create two directories:
>* `filepath pmp-desktop`: this is where you configure the project output files.
>* `filepath pmp-desktop/token`: this is where you add the Flash Player authorization token.
>   
>   
>1. Place the Flash Player authorization token you received from your Adobe Enablement Representative in the `filepath token` directory.
>   
>1. Rename the token to `filepath token.dat`.
>   
>1. Verify the token is accessible from `filepath http://www.yourhost.com/pmp-desktop/token/token.dat`, where `filepath www.yourhost.com` is your domain.
>   
>   

---
seo-title: Deploy the WAR files
title: Deploy the WAR files
uuid: 5456141e-5ba5-4481-ab48-c574a3bb81ab
index: y
internal: n
snippet: y
---

# Deploy the WAR files{#deploy-the-war-files}

1. Copy the WAR file to Tomcat’s [!DNL webapps] directory.

    * Individualization Server: [!DNL flashaccess.war] 
    * Key Generation Server: [!DNL flashaccess-kgs.war]

1. Copy the [!DNL ROOT] folder from the package provided by Adobe to the [!DNL webapps] directory.

   The Individualization server also needs to host the [!DNL crossdomain.xml] file. (The [!DNL ROOT] folder contains the [!DNL crossdomain.xml] file; [!DNL ROOT] must be in all caps.) The Key Generation server does not require this file. 


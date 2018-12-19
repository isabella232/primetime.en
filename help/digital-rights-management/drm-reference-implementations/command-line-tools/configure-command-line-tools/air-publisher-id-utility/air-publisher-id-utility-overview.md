---
seo-title: Overview
title: Overview
uuid: f45c6b58-53c5-41e0-be3d-590231dd214a
index: y
internal: n
snippet: y
---

# Overview{#overview}

When you build an AIR file, the AIR Developer Tool (ADT) automatically generates a Publisher ID. The AIR Publisher ID utility ( [!DNL AdobePublisherIDUtility.jar]) computes the Publisher ID for an AIR application.

The Publisher ID is unique to the certificate that you use to build an AIR file. If you reuse the same certificate for multiple AIR applications, all AIR applications have the same Publisher ID. An AIR release that succeeds release 1.5.2 does not add the generated Publisher ID to a file. Therefore, if you plan to use an AIR application whitelist, use this tool to determine the Publisher ID. 

>[!NOTE] {class="- topic/note "}
>
>The Publisher ID that is used for AIR whitelist enforcement is not the same as the Publisher ID that the application publisher specifies in the application's [!DNL application.xml] file.


---
seo-title: AIR Publisher ID utility overview
title: AIR Publisher ID utility overview
uuid: 073dfbb1-a1dd-4cc7-b1d4-51749604e72f
index: y
internal: n
snippet: y
---

# AIR Publisher ID utility overview{#air-publisher-id-utility-overview}

As part of the process of building an AIR file, the AIR Developer Tool (ADT) generates a Publisher ID. This is an identifier that is unique to the certificate used to build the AIR file. If you reuse the same certificate for multiple AIR applications, they will have the same Publisher ID.The AIR Publisher ID utility is used to compute the Publisher ID for an AIR application. AIR releases after 1.5.2 do not write the generated Publisher ID to a file, so it is necessary to use this tool to determine the Publisher ID if you are using an AIR application whitelist. 

>[!NOTE] {class="- topic/note "}
>
>The Publisher ID, used for AIR whitelist enforcement, is not the same as the Publisher ID specified by the application publisher in the application's [!DNL application.xml] file.


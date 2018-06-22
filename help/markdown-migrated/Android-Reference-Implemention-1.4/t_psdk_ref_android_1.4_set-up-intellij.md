---
description: If you are using IntelliJ, set up your environment as follows.
seo-description: If you are using IntelliJ, set up your environment as follows.
seo-title: IntelliJ setup instructions
title: IntelliJ setup instructions
---

# IntelliJ setup instructions

>1. Download and install IntelliJ IDEA Ultimate from [http://www.jetbrains.com/idea/download/](http://www.jetbrains.com/idea/download/).
>   Make sure to keep the Flash/Flex plug-in enabled during installation.
>   
>1. Start IntelliJ.
>   
>1. Select `uicontrol Open Project` and navigate to `filepath /projects/intellij` within your Primetime Reference project folder.
>   
>1. Click `uicontrol OK`.
>       
>   
>1. Add a new Flex/AIR SDK.
>1. From the top menu, select `uicontrol File` &gt; `uicontrol Project Structure`
>1. Under Project Settings, select `uicontrol Project`.
>1. Select `uicontrol New...` to add the new Flex/AIR SDK.
>1. Set the new Flex/AIR SDK to your Flex SDK directory (`filepath flex_sdk_4.6`):
>   
>   
>   
>1. Click `uicontrol Apply` to save your changes.
>   
>   
>1. Set the Flex/AIR SDK you just added to the project to each module's build configuration.
>1. From the top menu, select `uicontrol File` &gt; `uicontrol Project Structure`.
>1. Under Project Settings, select `uicontrol Modules`.
>1. For each module, click the arrow (Mac) or `uicontrol +` (Windows) next to the project name to expand the build configuration.
>1. Select the module's build configuration.
>1. Select the `uicontrol Dependencies` tab.
>1. Select the desired Flex/AIR SDK from the drop-down menu:
>1. Repeat steps 3. through 6. for each module in the list.
>1. Click `uicontrol OK` at the bottom of the window to accept the changes.
>   
>   
>1. From the top menu, select `uicontrol Build` &gt; `uicontrol Rebuild Project`.
>   >[!NOTE]
>   >
>   >The test project, ReferenceCoreTest, will not compile or run without first configuring the FlexUnit libraries. See "Setup FlexUnit Libraries" to compile the unit tests.
>   
>   
>   

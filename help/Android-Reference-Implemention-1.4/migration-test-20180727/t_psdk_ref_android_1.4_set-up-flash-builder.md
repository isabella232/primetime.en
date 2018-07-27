---
description: If you are using Flash Builder, set up your environment as follows.
seo-description: If you are using Flash Builder, set up your environment as follows.
seo-title: Flash Builder setup instructions
title: Flash Builder setup instructions
uuid: 691aa275-4596-4087-a01c-4d1d1c0cd7f2
index: n
internal: n
snippet: y
translate: y
---

# Flash Builder setup instructions

This guide assumes that you already requested a Flash Player Feature Authorization token.

>1. Create a new workspace in Flash Builder that is pointing to the `samples/ReferencePlayer/src/libs`folder that you created earlier in the process.
>1. Create a new substitution variable named `PMP_LOC` in the Eclipse workspace.

>   >[!NOTE]
>   >
>   >You need to do this now or you will not be able to import the projects into Flash Builder.
>
>   >1. In Eclipse, choose ** `Preferences` ** &gt; ** `General` ** &gt; ** `Workspace` ** &gt; ** `Linked Resources` **.
>   >1. Select ** `New...` **.
>   >1. Define a new path variable named `PMP_LOC`.
>   >   The value must be the full path name to your Primetime Reference source folder. For example, `/Users/username/Documents/PSDK-FlashRuntime/samples/PrimetimeReference/src`.>   >
>1. In Flash Builder, choose ** `File` ** &gt; ** `Import` **.
>1. Select ** `General` ** &gt; ** `Existing Projects into Workspace` **.

>1. In the Import dialog, choose ** `Select root directory` **.
>1. Click ** `Browse` ** and navigate to the `PrimetimeReference/projects/flashbuilder` folder within the main workspace folder that you created earlier in the process.

>1. Select all seven projects.
>1. Click ** `Finish` **.

>       [Change the project build order](http://help.adobe.com/en_US/flashbuilder/using/WSe4e4b720da9dedb524b8220812e5611f28f-7fef.html#WSe4e4b720da9dedb524b8220812e5611f28f-7fd1)The build order should be as follows: >    
>    * ToggleButton
>    * ReferenceCore
>    * AdvertisingOverlay
>    * ClosedCaptionMenu
>    * SettingsMenu
>    * ReferencePlaybar
>    * ReferencePlayer

>1. Select the ReferencePlayer project.
>1. Open the `PrimetimeReference.mxml` file and run it.

>       ** `Project` ** &gt; ** `Clean` ** &gt; ** `Clean All Projects` **
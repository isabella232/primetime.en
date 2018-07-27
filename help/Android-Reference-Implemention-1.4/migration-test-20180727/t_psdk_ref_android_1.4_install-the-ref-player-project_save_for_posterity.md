---
description: The Primetime Reference Implementation is an Android application built around the and AVE frameworks.
seo-description: The Primetime Reference Implementation is an Android application built around the and AVE frameworks.
seo-title: Build the Primetime Reference Implementation
title: Build the Primetime Reference Implementation
uuid: 38806874-6587-4468-81e9-b17fb3e47a8b
index: n
internal: n
snippet: y
translate: y
---

# Build the Primetime Reference Implementation

To setup and build the Primetime Reference Implementation in Eclipse:

>1. Extract the Primetime Reference Implementation from the  package to a directory of your choice.
>   You can find the Reference Implementation in the `samples/PrimetimeReference` directory.>
>1. Launch Eclipse.
>1. Select ** `File` ** &gt; ** `Import` **.
>1. Select ** `Android` ** &gt; ** `Existing Android Code Into Workspace` **.
>1. Click ** `Next` **.
>1. Use the ** `Browse` ** button to populate the Root Directory field with the location of the extracted Primetime Reference Implementation files (from Step 1).
>1. Select the following projects to import: ** `appcompat` **, ** `PrimetimeReference` **, and ** `PrimetimeReference/tests` **.
>1. Click ** `Finish` **.
>   If you didn’t modify your ** `Project` ** settings before importing projects, your project builds automatically at this point. If necessary, select  ** `Project` ** &gt; ** `Build Project` ** to build the project.
>   >[!NOTE]
>   >
>   >The ** `tests` ** project may encounter errors at this point, due to an order dependency that is fixed in the next step.
>
>1. Associate the tests project with the player project:
>   >1. Right-click ** `tests` ** and choose ** `Properties` **.
>   >1. Select ** `Java Build Path` **.
>   >1. Choose the ** `Projects` ** tab.
>   >1. Click ** `Add...` **.
>   >1. Select ** `CatalogActivity` **
>   >1. Click ** `OK` ** to close the ** `Required Project Selection` ** dialog.
>   >1. Click ** `OK` ** to close ** `Properties` **.
>1. Re-build the project.

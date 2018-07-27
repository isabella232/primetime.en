---
description: The Primetime Reference is an Android application built around the and AVE frameworks.
seo-description: The Primetime Reference is an Android application built around the and AVE frameworks.
seo-title: Build the Primetime reference implementation
title: Build the Primetime reference implementation
uuid: 7a259aa6-8626-4eb3-85ad-bf1ee5d83314
index: n
internal: n
snippet: y
translate: y
---

# Build the Primetime reference implementation

To set up and build the Primetime Reference project in Eclipse:

>1. Download the  Android zip file and unpack it into a directory in a location that you will remember.
>1. Launch Eclipse.
>1. Select ** `File` ** &gt; ** `Import` **.
>1. Select ** `Android` ** &gt; ** `Existing Android Code Into Workspace` **.
>1. Click ** `Next` **.
>1. Use the ** `Browse` ** button to populate the ** `Root Directory` ** field with the directory under `samples/PrimetimeReference/src` to which you unpacked the  Android zip file.
>1. Select the following projects to import: ** `appcompat` **, ** `PrimetimeReference` **.
>1. Click ** `Finish` **.
>1. Select  ** `Project` ** &gt; ** `Build Project` ** to build the project.
>   This step is not necessary if the project is set up to build automatically.>
>1. If you would like to include the tests project in the workspace, associate the tests project with the PrimetimeReference project:
>   >1. Repeat steps 3. through 6.
>   >1. Select the following project to import: `PrimetimeReference\tests`.
>   >1. Click ** `Finish` **.
>   >   The tests project has a dependency on the CatalogActivity project so you need to associate the tests project with the CatalogActivity project.>   >
>   >1. Right-click ** `tests` ** and choose ** `Properties` **.
>   >1. Select the ** `Projects` ** tab under Java Build Path.
>   >1. Click ** `Add...` **
>   >1. Select CatalogActivity.
>   >1. Click ** `OK` ** to add the project.
>   >1. Click ** `OK` ** to exit the Properties page.
>   >1. Select  ** `Project` ** &gt; ** `Build Project` ** to build the project.
>   >   This step is not necessary if the project is set up to build automatically.>   >

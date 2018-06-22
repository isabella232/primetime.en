---
description: The Primetime Reference is an Android application built around the and AVE frameworks.
seo-description: The Primetime Reference is an Android application built around the and AVE frameworks.
seo-title: Build the Primetime reference implementation
title: Build the Primetime reference implementation
---

# Build the Primetime reference implementation

To set up and build the Primetime Reference project in Eclipse:

>1. Download the  Android zip file and unpack it into a directory in a location that you will remember.
>   
>1. Launch Eclipse.
>   
>1. Select `uicontrol File` &gt; `uicontrol Import`.
>   
>1. Select `uicontrol Android` &gt; `uicontrol Existing Android Code Into Workspace`.
>   
>1. Click `uicontrol Next`.
>   
>1. Use the `uicontrol Browse` button to populate the `uicontrol Root Directory` field with the directory under `filepath samples/PrimetimeReference/src` to which you unpacked the  Android zip file.
>   
>1. Select the following projects to import: `uicontrol appcompat`, `uicontrol PrimetimeReference`.
>   
>1. Click `uicontrol Finish`.
>   
>1. Select  `uicontrol Project`  &gt; `uicontrol Build Project`  to build the project.
>   This step is not necessary if the project is set up to build automatically.
>   
>1. If you would like to include the tests project in the workspace, associate the tests project with the PrimetimeReference project:
>   >1. Repeat steps 3. through 6.
>   >   
>   >1. Select the following project to import: `codeph PrimetimeReference\tests`.
>   >   
>   >1. Click `uicontrol Finish`.
>   >   The tests project has a dependency on the CatalogActivity project so you need to associate the tests project with the CatalogActivity project.
>   >   
>   >1. Right-click `uicontrol tests` and choose `uicontrol Properties`.
>   >   
>   >1. Select the `uicontrol Projects` tab under Java Build Path.
>   >   
>   >1. Click `uicontrol Add...`
>   >   
>   >1. Select CatalogActivity.
>   >   
>   >1. Click `uicontrol OK` to add the project.
>   >   
>   >1. Click `uicontrol OK` to exit the Properties page.
>   >   
>   >1. Select  `uicontrol Project`  &gt; `uicontrol Build Project`  to build the project.
>   >   This step is not necessary if the project is set up to build automatically.
>   >   
>   >   
>   
>   

---
description: The Primetime Reference Implementation is an Android application built around the and AVE frameworks.
seo-description: The Primetime Reference Implementation is an Android application built around the and AVE frameworks.
seo-title: Build the Primetime Reference Implementation
title: Build the Primetime Reference Implementation
---

# Build the Primetime Reference Implementation

To setup and build the Primetime Reference Implementation in Eclipse:

>1. Extract the Primetime Reference Implementation from the  package to a directory of your choice.
>   You can find the Reference Implementation in the`filepath samples/PrimetimeReference` directory.
>   
>1. Launch Eclipse.
>   
>1. Select `uicontrol File` &gt; `uicontrol Import`.
>   
>1. Select `uicontrol Android` &gt; `uicontrol Existing Android Code Into Workspace`.
>   
>1. Click `uicontrol Next`.
>   
>1. Use the `uicontrol Browse` button to populate the Root Directory field with the location of the extracted Primetime Reference Implementation files (from Step 1).
>   
>1. Select the following projects to import: `uicontrol appcompat`, `uicontrol PrimetimeReference`, and `uicontrol PrimetimeReference/tests`.
>   
>1. Click `uicontrol Finish`.
>   If you didn’t modify your `uicontrol Project`  settings before importing projects, your project builds automatically at this point. If necessary, select  `uicontrol Project`  &gt; `uicontrol Build Project`  to build the project.
>   >[!NOTE]
>   >
>   >The`uicontrol tests` project may encounter errors at this point, due to an order dependency that is fixed in the next step.
>   
>   
>1. Associate the tests project with the player project:
>   >1. Right-click `uicontrol tests` and choose `uicontrol Properties`.
>   >   
>   >1. Select `uicontrol Java Build Path`.
>   >   
>   >1. Choose the `uicontrol Projects` tab.
>   >   
>   >1. Click `uicontrol Add...`.
>   >   
>   >1. Select `uicontrol CatalogActivity`
>   >   
>   >1. Click `uicontrol OK` to close the `uicontrol Required Project Selection` dialog.
>   >   
>   >1. Click `uicontrol OK` to close `uicontrol Properties`.
>   >   
>   >   
>   
>1. Re-build the project.
>   
>   

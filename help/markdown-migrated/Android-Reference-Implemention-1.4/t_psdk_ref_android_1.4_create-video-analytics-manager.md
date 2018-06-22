---
description: 
seo-description: 
seo-title: Create the Video Analytics Manager
title: Create the Video Analytics Manager
---

# Create the Video Analytics Manager

A new manager class ( `codeph  VAManager`) has been added to the Android Reference Implementation. `codeph  VAManager` simply creates and destroys an instance of the `codeph  VideoHeartbeat` class. The reference implementation creates a `codeph  VAManager` instance when a new `codeph  MediaPlayer` is created, and destroys that instance when the `codeph  MediaPlayer` is destroyed. This is implemented in `codeph  PlayerFragment.java`.

>1. To create a new Video Analytics Manager:
>   ```java
>   VAManager vaManager = ManagerFactory.getVAManager(true, config, mediaPlayer); 
>   vaManager.createVAProvider(getActivity().getApplicationContext());
>   ```
>   
>       
>       The config variable is a concrete implementation of `codeph  IVAConfig` and contains the runtime `codeph  VideoHeartbeat` configurations.
>       >[!NOTE]
>       >
>       >If the Android application is not configured with an Adobe Analytics account, then video tracking data will not be generated, even if an instance of`codeph  VAManager` is created and enabled.
>       
>       
>   
>   

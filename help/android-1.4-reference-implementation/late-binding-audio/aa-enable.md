---
description: You can integrate late-binding or alternate audio streams into your player by creating an alternate audio feature manager.
seo-description: You can integrate late-binding or alternate audio streams into your player by creating an alternate audio feature manager.
seo-title: Integrate late-binding audio
title: Integrate late-binding audio
uuid: cd2e259a-2af4-4d7b-a856-79bd087e8ca6
index: y
internal: n
snippet: y
---

# Integrate late-binding audio {#integrate-late-binding-audio}

You can integrate late-binding or alternate audio streams into your player by creating an alternate audio feature manager.

* To create an alternate audio manager:

  ```java
  AAManager aaManager = new AAManagerOn(); 
  ```

* To use the ManagerFactory to enable alternate audio, make sure the following line of code is in the `PlayerFragment.java` file:

  ```java
  aaManager = ManagerFactory.getAAManager( 
  <b>true</b>,config, mediaPlayer);
  ```

  To disable alternate audio:

  ```java
  aaManager = ManagerFactory.getAAManager( 
  <b>false</b>,config, mediaPlayer);
  ```


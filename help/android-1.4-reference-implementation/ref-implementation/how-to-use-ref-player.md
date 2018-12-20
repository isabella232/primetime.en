---
seo-title: How to use the Primetime reference implementation
title: How to use the Primetime reference implementation
uuid: 9eb262c4-d987-493a-92a4-311118c5f01e
---

# How to use the Primetime reference implementation{#how-to-use-the-primetime-reference-implementation}

The Primetime reference implementation is a modular player that has been broken down into individual features that you can easily modify through specialized feature managers. These feature managers are used as a bridge to connect the application and the TVSDK library.

You can use the reference implementation in the following ways:

* Use it as-is without changing any code (all features are turned on with default values). 
* Use it as a reference to understand how to use the TVSDK library. 
* Pick and choose the features that apply to your application by turning off the features that you don't use. 
* Customize the UI components without making any changes to the features.

We provide the Primetime reference implementation to help you understand the TVSDK and easily modify the feature managers to customize your player. However, please refer to the [TVSDK 1.4 for Android Programmer's Guide](http://help.adobe.com/en_US/primetime/psdk/android/index.html) for detailed information about the TVSDK library.

For easy access to the reference implementation API documentation in Javadoc format, click [here](http://help.adobe.com/en_US/primetime/reference_implementation/android/javadoc/index.html). 

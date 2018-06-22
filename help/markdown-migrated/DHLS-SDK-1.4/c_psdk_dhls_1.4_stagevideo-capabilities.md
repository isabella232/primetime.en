---
description: On devices that support GPU (hardware) acceleration, you can use a flash.media.StageVideo object to process video on the device hardware. The availability of StageVideo depends upon the versions and capabilities of different parts of your system including Flash Player, video hardware, OS, drivers, browser, network connection, and viewing context.
seo-description: On devices that support GPU (hardware) acceleration, you can use a flash.media.StageVideo object to process video on the device hardware. The availability of StageVideo depends upon the versions and capabilities of different parts of your system including Flash Player, video hardware, OS, drivers, browser, network connection, and viewing context.
seo-title: StageVideo capabilities and restrictions
title: StageVideo capabilities and restrictions
---

# StageVideo capabilities and restrictions

The `codeph StageVideo` class lets you take advantage of hardware acceleration to present video at the highest possible performance level for a device. The availability and performance of `codeph StageVideo` is affected by the following factors:

* **Hardware acceleration** - When hardware acceleration is available, `codeph StageVideo` processes video on the device hardware. When hardware acceleration is not available, the `codeph StageVideo` responds depends on which version of Flash you are running:
    * *Flash 15 and later* - When hardware acceleration is not available, `codeph StageVideo` falls back to software, and you do not have to do anything.
      >[!TIP]
      >
      >When hardware acceleration is not available, performance can degrade significantly.
      
    * *Flash 14 and earlier* - When hardware acceleration is not available, `codeph StageVideo` becomes unavailable. In a small set of configurations where hardware acceleration is not supported by the browser or GPU, or is turned off in the Flash Player, video display with the  HLS stack will fail. In the *HDS* pipeline, you can switch from `codeph StageVideo` to an alternate, such as the Video object, that processes video in the CPU.
  
* **Presentation context** - During full screen viewing, `codeph StageVideo` is always available and performance will be at the maximum level that is available on the device. When not viewing full-screen, the video presentation falls under the context of the browser, where the browser's settings and capabilities are used.
* **wmode** - In the browser context, the `codeph wmode` setting is critical to performance. Adobe recommends that you keep `codeph wmode` set to `codeph direct` to ensure the best possible performance in the browser context.
  >[!NOTE] {type="remember"}
  >
  >The combination of factors that include`codeph wmode`, `codeph StageVideo`, and Flash result in different capabilities and restrictions, depending upon how fast your hardware runs and which version of Flash you are using.
    * *Flash 15 and later* - `codeph StageVideo` is available with all available `codeph wmode` settings. However, if you set `codeph wmode` to a setting other than `codeph direct`, performance will be lower.
    * *Flash 14 and earlier* - If you set `codeph wmode` to a setting other than `codeph direct`, `codeph StageVideo` is not available in all browsers.
  

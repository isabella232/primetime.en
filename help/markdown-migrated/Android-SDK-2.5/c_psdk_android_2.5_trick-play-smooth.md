---
description: If your system has access to hardware-assisted decoding, you can achieve smoother trick play than with the pure software implementation by using iFrame format.
seo-description: If your system has access to hardware-assisted decoding, you can achieve smoother trick play than with the pure software implementation by using iFrame format.
seo-title: Smoother trick play operations
title: Smoother trick play operations
---

# Smoother trick play operations

<a id="section_3DBFD7A3D1C7453096D3D3885E786263"></a>

Using iFrame format results in trick play operations that are not smooth. Smoother trick play operation uses a normal (not iFrame) profile, hardware decoding support, and an increased frame rate. Different hardware-assisted decoding devices have different capabilities. Double speed requires 60 frames per second (FPS), and quadruple speed requires 120 FPS.

>[!IMPORTANT]
>
>Adobe recommends that you limit playback to double speed for newer Android devices and not use the feature for older Android devices.
To achieve smoother trick play, set `codeph ABRControlParameters.maxPlayoutRate` to the desired multiple of normal speed (for example, 2.0 for double speed). If a subsequent call to `codeph MediaPlayer.setRate()` has an argument that is less than or equal to the value you set for `codeph maxPlayoutRate`,  uses a normal profile to achieve smoother trick play. Otherwise it uses an iFrame profile for the trickplay operation.


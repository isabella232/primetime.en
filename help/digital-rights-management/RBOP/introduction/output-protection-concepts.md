---
description: This section provides a conceptual overview of the configuration, options, and meanings associated with output protection.
seo-description: This section provides a conceptual overview of the configuration, options, and meanings associated with output protection.
seo-title: RBOP Concepts
title: RBOP Concepts
uuid: 04f275ea-88d2-4218-bebf-5d86c434fea3
index: y
internal: n
snippet: y
---

# RBOP Concepts{#rbop-concepts}

This section provides a conceptual overview of the configuration, options, and meanings associated with output protection.

You specify your resolution-based output protection requirements in a hierarchical JSON structure. *The output requirements are pixel-based.*

At the highest level of the JSON specification, you can define maximum pixel resolution, and pixel constraints for specified resolutions:

* `maxPixel` - The maximum pixel resolution defines the maximum resolution for which decryption will occur. 
* `pixelConstraints` - Pixel constraints define output requirements that must be enforced for a specified resolution.

You associate output requirements with specific pixel constraints. The types of requirements that you can associate with a given pixel constraint include restrictions for digital, analog, and over-the-air (OTA) connections.

**Digital Ouput **

The digital output requirement can specify restrictive options, such as "digital output protection is required," or "playback is not permitted". Output requirements can also specify less restrictive options such as, "no protection should be applied," or "digital protection should be used if it is available."

**Analog Output**

Analog output connections are simpler than digital output; they consist of a single output requirement. 

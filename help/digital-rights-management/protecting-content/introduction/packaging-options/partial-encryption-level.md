---
seo-title: Partial encryption level
title: Partial encryption level
uuid: dbd9ce92-c829-4cad-9ac4-c57bd4f70345
---

# Partial encryption level {#partial-encryption-level}

This packaging option specifies whether all frames, or only a subset of frames, should be encrypted. There are three levels of encryption: low, medium and high.

>[!NOTE] {class="- topic/note "}
>
>Partial encryption applies to the video track in F4V/MP4 files only.

Partial encryption is designed to give content providers granularity to encode the content in parts. Encryption of content adds CPU overhead to the device that is decrypting and viewing the content. Use partial encryption to reduce CPU overhead while maintaining very strong protection of the content. A motivating case for using this feature is a single piece of content that is intended to be playable across low, medium, and high powered devices.

Due to the nature of video encoding, it is not necessary to encrypt 100% of video to make it unplayable if it is stolen. Partial encryption has three settings, low, medium, and high, and the associated percentages of encryption are dependent upon how the video is encoded. Because of this encoding dependency, the percentage of your content that is encrypted falls within the following ranges:

* High: Encrypts all samples. 
* Medium: Encrypts a target 50% of the data. 
* Low: Encrypts a target 20 to 30% of the data.

These settings were designed using the following rule: Any content that is encrypted at the low setting is also encrypted at the medium setting. This ensures that the same piece of content distributed at low encryption by one party and distributed at medium encryption by another party does not compromise the protection of the content.

Example use case: Reducing the encryption level decreases the decryption overhead on the client and improves playback performance on low-end machines. 

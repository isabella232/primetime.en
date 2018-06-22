---
---

<a id="section_B09A012C97454AF58CE2269B800D8027"></a>

The  library provides a simple means to load and prepare content for playback by using the `codeph replaceCurrentResource` method in the `codeph MediaPlayer` interface. This method receives an instance of the `codeph MediaResource` class as the sole input argument. The `codeph MediaResource` class is composed of the following information:
* A URL, which represents the location of the content that is about to be loaded.
* A type, which is the type of content that is about to be loaded.
  This is a string that defines the types of content that can be loaded by the `codeph MediaPlayer`. Possible values are HLS and HDS. Each value is associated with the string representing the file extensions commonly used, “m3u8” for HLS and “f4m” for HDS.
  
  
* Some metadata, which is an instance of the `codeph Metadata` class.
  This dictionary-like structure might contain additional information about the content that is about to be loaded, such as information about the alternate/ad content that should be placed in the main content.
  
  

The metadata is the medium through which information that is related to alternate content is passed to . The `codeph Metadata` interface defines the API for a generic key-value store, where both the key and the value are plain strings.


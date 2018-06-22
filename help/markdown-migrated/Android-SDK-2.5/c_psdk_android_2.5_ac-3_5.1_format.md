---
description: The Audio Codec 3 (AC-3, also known as Dolby Digital®) 5.1 format, allows content providers to compress the size of multichannel audio files without impairing the sound quality. AC-3 is a 5.1 format, which means that it provides five full-bandwidth channels for a richer user experience.
seo-description: The Audio Codec 3 (AC-3, also known as Dolby Digital®) 5.1 format, allows content providers to compress the size of multichannel audio files without impairing the sound quality. AC-3 is a 5.1 format, which means that it provides five full-bandwidth channels for a richer user experience.
seo-title: AC-3 5.1 format
title: AC-3 5.1 format
---

# AC-3 5.1 format

For more information, see [Dolby Digital 5.1](http://www.dolby.com/us/en/technologies/dolby-digital.html).

supports the following AC-3 5.1 features:
* AC-3 surround audio
* Mixed/unmixed streams for surround audio type
* Ability to query the device to see if the surround audio codec is available on the device.
  The results determine which preferred audio codec type is selected. The manifest with audio codec type that the device is not going to use is discarded. For example, if the AC-3 format has been selected, profiles with the Advanced Audio Coding (AAC) format are not considered.
  
  
* Passthrough mode
  In passthrough mode, instead of decoding the media from the AC-3 5.1 format to a multichannel pulse-code modulation (PCM) format, the  gets modified or unmodified (depending on the device) Dolby media from the Decoder. This media is sent to the audio device (speaker or receiver) so that the audio device can decode and play back the Dolby surround stream.
  
  

>[!IMPORTANT]
>
>supports the AC-3 5.1 features only on the device Amazon Fire TV 1st generation.
The following AC-3 5.1 features are not supported:
* Multichannel AAC audio
* ABR across different codecs (AAC - AC3)

## Selecting supported media {#section_0D7E717BE18B418D817EE017EF2375D1}

Here is the typical workflow that occurs when  finds a manifest with AC-3 and AAC media:
1. queries which codec the device can support.
1. The codec with the higher quality is selected.
   Here is the order in which quality is selected:
    1. AC-3
    1. AAC
   
   
1. ignores profiles with other audio codec types.
>[!TIP]
>
>The application cannot obtain information about ignored profiles.

## Determining the output mode {#section_D2AFBF33D3904AC2A7C653A60C3A0CD3}

<table id="table_D502BA77AAB4455E86DD0F6B417C5629"> 
 <tgroup cols="3"> 
  <colspec colnum="1" colname="col1" colwidth="*" /> 
  <colspec colnum="2" colname="col2" colwidth="*" /> 
  <colspec colnum="3" colname="col3" colwidth="*" /> 
  <thead> 
   <tr> 
    <th colname="col1" class="entry"> </th> 
    <th colname="col2" class="entry">Surround sound</th> 
    <th colname="col3" class="entry">Stereo speaker</th> 
   </tr> 
  </thead> 
  <tbody> 
   <tr> 
    <td colname="col1">Device configuration Dolby on (or auto)</td> 
    <td colname="col2">Device configuration Dolby on (or auto)</td> 
    <td colname="col3">Stereo mode</td> 
   </tr> 
   <tr> 
    <td colname="col1">Device configuration Dolby off</td> 
    <td colname="col2">Stereo mode</td> 
    <td colname="col3">Stereo mode</td> 
   </tr> 
  </tbody> 
 </tgroup> 
</table>

While processing AC-3 media, if an Android device is connected to the speaker system, the decision to play content in surround mode or stereo mode depends on how the device is configured.


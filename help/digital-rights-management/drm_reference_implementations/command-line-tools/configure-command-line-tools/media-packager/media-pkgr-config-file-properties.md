---
description: null
seo-description: null
seo-title: Configuration properties
title: Configuration properties
uuid: b4d0b545-6043-43c9-8769-fb872895356f
index: y
internal: n
snippet: y
---

# Configuration properties{#configuration-properties}

<a id="section_3081C60BE54D47569FD1E3793513A2D9"></a>

>[!NOTE]
>
>For property names that include* n*, *n* represents an integer that starts with 1 and increases for each instance of the property.

<table frame="all" colsep="1" rowsep="1" class="+ topic/table adobe-d/table " id="table_dx4_mpy_n4"> 
 <thead class="- topic/thead "> 
  <tr rowsep="1" class="- topic/row "> 
   <th colname="1" class="- topic/entry entry"> <p class="- topic/p ">Property </p> </th> 
   <th colname="2" class="- topic/entry entry"> <p class="- topic/p ">Description </p> </th> 
  </tr> 
 </thead>
 <tbody class="- topic/tbody "> 
  <tr rowsep="1" class="- topic/row "> 
   <td colname="1" class="- topic/entry "><span class="codeph"> encrypt.contents.video</span> </td> 
   <td colname="2" class="- topic/entry "> Indicates whether to encrypt video content. </td> 
  </tr> 
  <tr rowsep="1" class="- topic/row "> 
   <td colname="1" class="- topic/entry "><span class="codeph"> encrypt.contents.audio</span> </td> 
   <td colname="2" class="- topic/entry "> Indicates whether to encrypt audio. </td> 
  </tr> 
  <tr rowsep="1" class="- topic/row "> 
   <td colname="1" class="- topic/entry "><span class="codeph"> encrypt.contents.script</span> </td> 
   <td colname="2" class="- topic/entry "> <p>Indicates whether to encrypt script data in mp4s. </p> <p><i class="+ topic/ph hi-d/i ">onMetaData</i> and <i class="+ topic/ph hi-d/i ">onXMP</i> script data tags are never encrypted even if you enable this option. </p> </td> 
  </tr> 
  <tr rowsep="1" class="- topic/row "> 
   <td colname="1" class="- topic/entry "><span class="codeph"> encrypt.contents.video.level</span> </td> 
   <td colname="2" class="- topic/entry "> <p class="- topic/p ">Indicates the video encryption level. </p> <p class="- topic/p ">A value of <span class="codeph"> high</span> is used to encrypt all video content, while values of <span class="codeph"> medium</span> and <span class="codeph"> low</span> are used to encrypt portions of the video content for mp4 files that include H.264 content. </p> <p class="- topic/p ">value = <span class="codeph"> high | medium | low</span> </p> </td> 
  </tr> 
  <tr rowsep="1" class="- topic/row "> 
   <td colname="1" class="- topic/entry "><span class="codeph"> encrypt.contents.secondsUnencrypted</span> </td> 
   <td colname="2" class="- topic/entry "> <p class="- topic/p ">If a value is greater than 0, then the specified number of seconds of content at the beginning of the file are not encrypted. </p> </td> 
  </tr> 
  <tr rowsep="1" class="- topic/row "> 
   <td colname="1" class="- topic/entry "><span class="codeph"> encrypt.keys.asymmetric.certfile</span> </td> 
   <td colname="2" class="- topic/entry "> <p class="- topic/p ">The license server certificate file used to encrypt the key. </p> <p class="- topic/p ">The <span class="codeph"> encrypt.keys.asymmetric.certfile</span> property specifies a file that includes the certificate only (either PEM or DER format is acceptable). </p> </td> 
  </tr> 
  <tr rowsep="1" class="- topic/row "> 
   <td colname="1" class="- topic/entry "><span class="+ topic/ph pr-d/codeph codeph">encrypt.keys.policyFile.n</span> </td> 
   <td colname="2" class="- topic/entry "> <p class="- topic/p ">This property is used repeatedly to create a list of DRM policies to apply to the content. <span class="codeph"> n</span> represents an integer whose value is 1 or greater. The client uses the first instance by default. </p> </td> 
  </tr> 
  <tr rowsep="1" class="- topic/row "> 
   <td colname="1" class="- topic/entry "><span class="codeph"> encrypt.license.serverurl</span> </td> 
   <td colname="2" class="- topic/entry "> <p class="- topic/p ">The license server URL </p> </td> 
  </tr> 
  <tr rowsep="1" class="- topic/row "> 
   <td colname="1" class="- topic/entry "><span class="codeph"> encrypt.license.servercert</span> </td> 
   <td colname="2" class="- topic/entry "> <p class="- topic/p ">The transport certificate for the license server. </p> <p class="- topic/p ">This property specifies a <span class="filepath"> .cer</span> file that includes the certificate only (either PEM or DER format is acceptable). </p> </td> 
  </tr> 
  <tr rowsep="1" class="- topic/row "> 
   <td colname="1" class="- topic/entry "><span class="codeph"> encrypt.sign.certfile</span> </td> 
   <td colname="2" class="- topic/entry "> <p class="- topic/p ">The PKCS12 file that includes packager credentials for signing content. </p> <p class="- topic/p ">The <span class="codeph"> encrypt.sign.certfile</span> needs to refer to a <span class="filepath"> .pfx</span> file that includes a certificate and private key. </p> </td> 
  </tr> 
  <tr rowsep="1" class="- topic/row "> 
   <td colname="1" class="- topic/entry "><span class="codeph"> encrypt.sign.certpass</span> </td> 
   <td colname="2" class="- topic/entry "> <p class="- topic/p ">The password that you can apply to protect the file which has been specified by <span class="codeph"> encrypt.sign.certfile</span>. </p> </td> 
  </tr> 
  <tr rowsep="1" class="- topic/row "> 
   <td colname="1" class="- topic/entry "><span class="codeph"> encrypt.license.minServerVersion</span> </td> 
   <td colname="2" class="- topic/entry "> <p class="- topic/p ">Sets the minimum server version that is required to issue licenses for the content being packaged. </p> <p class="- topic/p ">Specify x (for Primetime DRM x.0) where x represents a major release number. Any versions of servers that precede Adobe Primetime version 3.0 do not support this setting. </p> </td> 
  </tr> 
  <tr rowsep="1" class="- topic/row "> 
   <td colname="1" class="- topic/entry "><span class="codeph">encrypt.keys.policyFile.n .domain.transportcert </span> </td> 
   <td colname="2" class="- topic/entry "> <p class="- topic/p ">If a DRM policy <span class="+ topic/ph pr-d/codeph codeph"> encrypt.keys.policyFile.n</span> requires domain registration with a server that supports a transport certificate other than the one that you have specified in <span class="+ topic/ph pr-d/codeph codeph"> encrypt.license.servercert</span>, then you need to provide the domain transport certificate needs. </p> <p class="- topic/p ">This property specifies a file that includes the certificate only (either PEM or DER format is acceptable). </p> </td> 
  </tr> 
  <tr rowsep="1" class="- topic/row "> 
   <td colname="1" class="- topic/entry "><span class="codeph"> encrypt.keys.licenseKey</span> </td> 
   <td colname="2" class="- topic/entry "> <p class="- topic/p ">Specifies a license key. </p> <p class="- topic/p ">If you do not specify a key, then the key is randomly generated. When you do not enable key rotation, then you can use this key to encrypt content. </p> <p class="- topic/p ">When you enable key rotation, you can use this key to protect the rotation keys. The key must be 16 bytes in length and be specified as Hex values. Whitespace between the Hex values is optional. </p> </td> 
  </tr> 
  <tr rowsep="1" class="- topic/row "> 
   <td colname="1" class="- topic/entry "><span class="codeph"> encrypt.keys.rotation.enable</span> </td> 
   <td colname="2" class="- topic/entry "> <p class="- topic/p ">Specifies whether key rotation is enabled. </p> <p class="- topic/p ">If set to false, which is the default setting, then key rotation is disabled and the master CEK is used to encrypt all samples in the content. </p> <p class="- topic/p ">If set to true, key rotation is enabled and different keys can be used to encrypt segments of any content. </p> </td> 
  </tr> 
  <tr rowsep="1" class="- topic/row "> 
   <td colname="1" class="- topic/entry "><span class="codeph">encrypt.keys.rotation.key.n</span> </td> 
   <td colname="2" class="- topic/entry "> <p class="- topic/p ">Sequence of rotated keys that you can specify to encrypt content when key rotation is enabled. </p> <p class="- topic/p ">If you do not specify any keys, then keys are randomly generated. The keys must be 16 bytes in length and specified as Hex values. </p> <p class="- topic/p ">Whitespace between the Hex values is optional. <i class="+ topic/ph hi-d/i ">n</i> must be monotonically increasing, starting from 1. When you specify multiple keys, then keys are cycled through in the order that you indicated. </p> </td> 
  </tr> 
  <tr rowsep="1" class="- topic/row "> 
   <td colname="1" class="- topic/entry "><span class="codeph"> encrypt.keys.rotation.interval</span> </td> 
   <td colname="2" class="- topic/entry "> <p class="- topic/p ">Specifies the interval of time in seconds during which you can apply a rotation key to encrypt content samples. </p> <p class="- topic/p ">After the interval of time has elapsed in which the content has been encrypted, then the next rotation key is then applied. If you have enabled key rotation but have not specified any interval of time, then the keys are automatically rotated every 15 minutes. </p> </td> 
  </tr> 
  <tr rowsep="0" class="- topic/row "> 
   <td colname="1" class="- topic/entry "><span class="codeph"> encrypt.license.serverless</span> </td> 
   <td colname="2" class="- topic/entry "> <p class="- topic/p ">If this option is set to true, then a license server from which licenses can be obtained is not available. </p> <p class="- topic/p ">Licenses must be embedded or obtained out-of-band. The default value is set to false unless you specify a different value. This option is only supported in Primetime DRM Professional. </p> </td> 
  </tr> 
 </tbody> 
</table>


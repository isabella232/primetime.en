---
description: null
seo-description: null
seo-title: Media Packager command-line usage
title: Media Packager command-line usage
uuid: 5814a465-fa49-4ed0-b5d6-c18d64167a9f
---

# Media Packager command-line usage{#media-packager-command-line-usage}

**Package one file:**

```
java -jar AdobePackager.jar  
<i class="+ topic ph hi-d="" i "="">
  source  
 <i class="+ topic ph hi-d="" i "="">
   dest [ 
  <i class="+ topic ph hi-d="" i "="">
    options] 
  </i class="+ topic> 
 </i class="+ topic> 
</i class="+ topic>
```

* `source` - The name of the file that you want to encrypt. 
* `dest` - The name of the resulting encrypted file.

  If you specify a directory, then the encrypted file is automatically saved in the specified directory with the same file name that you specified as the source file. However, you cannot specify a destination directory that includes the source file.

**Package multiple files with the same key** (for multi-bit-rate support):

```
java -jar AdobePackager.jar  
<i class="+ topic ph hi-d="" i "="">
  sourcefiles  
 <i class="+ topic ph hi-d="" i "="">
   dest-directory [ 
  <i class="+ topic ph hi-d="" i "="">
    options] 
  </i class="+ topic> 
 </i class="+ topic> 
</i class="+ topic>
```

* `sourcefiles` - A series of whitespace-delimited source entries for the files that you want to encrypt. 
* `dest-directory` - The destination directory where you want to write encrypted content. The encrypted files are automatically saved in this directory using the same file names as the source files. However, the destination directory cannot include any source files.

**View information about an encrypted file:**

```
java -jar AdobePackager.jar -d  
<i class="+ topic ph hi-d="" i "="">
  encryptedfile [-e] [-m] 
</i class="+ topic>
```

**View information about a metadata file:**

```
java -jar AdobePackager.jar -dm <metadatafile> [-e]
```

* `metadatafile` is a [!DNL .metadata] file that includes DRM metadata.

>[!NOTE] {class="- topic/note "}
>
>During packaging, the Media Packager can no longer generate a [!DNL .header] file by default. To generate a [!DNL .header] file, use the `-h` option during packaging.

## Options:

<table frame="all" colsep="1" rowsep="1" class="+ topic/table adobe-d/table " id="table_wgz_spy_n4">  
 <thead class="- topic/thead "> 
  <tr rowsep="1" class="- topic/row "> 
   <th colname="1" class="- topic/entry entry"> <p class="- topic/p ">Command line option </p> </th> 
   <th colname="2" class="- topic/entry entry"> <p class="- topic/p ">Description </p> </th> 
  </tr> 
 </thead>
 <tbody class="- topic/tbody "> 
  <tr rowsep="1" class="- topic/row "> 
   <td colname="1" class="- topic/entry "> <p class="- topic/p ">-c <span class="+ topic/ph pr-d/codeph codeph"> configfile </span> </p> </td> 
   <td colname="2" class="- topic/entry "> <p class="- topic/p ">Specifies the name and location of the configuration file. </p> <p class="- topic/p ">If you do not specify a name or a location, the DRM Media Packager searches for <span class="filepath"> flashaccesstools.properties </span> in the current working directory. </p> <p>Note:  Options that you specify on the command line take precedence over the options you specify in the configuration file. </p> </td> 
  </tr> 
  <tr rowsep="1" class="- topic/row "> 
   <td colname="1" class="- topic/entry "> <p class="- topic/p ">-d <span class="+ topic/ph pr-d/codeph codeph"> encryptedfile </span> </p> </td> 
   <td colname="2" class="- topic/entry "> <p class="- topic/p ">Enables you to view information about a file that has already been packaged. </p> <p class="- topic/p ">The source and destination files are not required. </p> </td> 
  </tr> 
  <tr rowsep="1" class="- topic/row "> 
   <td colname="1" class="- topic/entry "> <p class="- topic/p ">-dm <span class="+ topic/ph pr-d/codeph codeph"> metadatafile </span> </p> </td> 
   <td colname="2" class="- topic/entry "> <p class="- topic/p ">Enables you to view information about existing metadata. </p> <p class="- topic/p ">The source and destination files are not required. </p> </td> 
  </tr> 
  <tr rowsep="1" class="- topic/row "> 
   <td colname="1" class="- topic/entry "> <p class="- topic/p ">-e </p> </td> 
   <td colname="2" class="- topic/entry "> <p class="- topic/p ">Extracts DRM policies from a packaged file when you apply this option in conjunction with the <span class="codeph"> -d </span> option. </p> <p class="- topic/p ">A file is automatically created in the same directory in which the encrypted file is located with a file name and DRM policy identifier. </p> </td> 
  </tr> 
  <tr rowsep="1" class="- topic/row "> 
   <td colname="1" class="- topic/entry "> <p class="- topic/p ">-h </p> </td> 
   <td colname="2" class="- topic/entry "> <p class="- topic/p ">Extracts the DRM header from a packaged file when you apply this option in conjunction with the <span class="codeph"> -d </span> option. </p> <p class="- topic/p ">A file is automatically created in the same directory in which the encrypted file, is located with the file name and the extension <span class="filepath"> .header </span>. </p> </td> 
  </tr> 
  <tr rowsep="1" class="- topic/row "> 
   <td colname="1" class="- topic/entry "> <p class="- topic/p ">-i <span class="+ topic/ph pr-d/codeph codeph"> contentID </span> </p> </td> 
   <td colname="2" class="- topic/entry "> <p class="- topic/p ">Specifies a unique identifier for this segment of content. </p> <p class="- topic/p ">If you do not specify an identifier, then the destfile file name is automatically applied. </p> </td> 
  </tr> 
  <tr rowsep="1" class="- topic/row "> 
   <td colname="1" class="- topic/entry "> <p class="- topic/p ">-k <span class="+ topic/ph pr-d/codeph codeph"> key </span>= <span class="+ topic/ph pr-d/codeph codeph"> value </span> </p> </td> 
   <td colname="2" class="- topic/entry "> <p class="- topic/p ">Specifies a custom key/value to add to content metadata. </p> <p class="- topic/p ">You can specify multiple <span class="codeph"> -k </span> options. </p> </td> 
  </tr> 
  <tr rowsep="1" class="- topic/row "> 
   <td colname="1" class="- topic/entry "> <p class="- topic/p ">-m </p> </td> 
   <td colname="2" class="- topic/entry "> <p class="- topic/p ">Extract metadata from a packaged file when you apply this option in conjunction with the <span class="codeph"> -d </span> option. </p> <p class="- topic/p ">A file is automatically created in the same directory as the encrypted file with a file name and a <span class="codeph"> .metadata </span> extension. </p> </td> 
  </tr> 
  <tr rowsep="1" class="- topic/row "> 
   <td colname="1" class="- topic/entry "> <p class="- topic/p ">-noprompt </p> </td> 
   <td colname="2" class="- topic/entry "> <p class="- topic/p ">Do not ask whether the destination file should be overwritten. </p> <p class="- topic/p ">If the destination file already exists and <span class="codeph"> -o </span> is not set, then an error occurs. </p> </td> 
  </tr> 
  <tr rowsep="1" class="- topic/row "> 
   <td colname="1" class="- topic/entry "> <p class="- topic/p ">-o </p> </td> 
   <td colname="2" class="- topic/entry "> <p class="- topic/p ">Overwrites the destination file without you being prompted unless it already exists. </p> </td> 
  </tr> 
  <tr rowsep="0" class="- topic/row "> 
   <td colname="1" class="- topic/entry "> <p class="- topic/p ">-p <span class="+ topic/ph pr-d/codeph codeph"> filename [domain-transport-cert] </span> </p> </td> 
   <td colname="2" class="- topic/entry "> <p class="- topic/p ">Specifies the name of the file that includes the DRM policy. </p> <p class="- topic/p ">If the DRM policy requires domain registration with a server that uses a transport certificate other than the one that you have specified in the properties file, then you need to provide the domain transport certificate. </p> <p class="- topic/p ">You can specify multiple <span class="codeph"> -p </span> options. The client always applies the first option by default. The values that you have specified on the command line takes precedence over those that you have specified in the configuration file. </p> </td> 
  </tr> 
 </tbody> 
</table>


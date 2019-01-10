---
seo-title: Packager Preferences
title: Packager Preferences
uuid: 3e9c971d-3a5f-4f3e-97e7-baab63b1f67f
index: y
internal: n
snippet: y
---

# Packager Preferences{#packager-preferences}

This tab contains settings required for packaging content. The following table describes these preferences: 

<table frame="all" colsep="1" rowsep="1" class="+ topic/table adobe-d/table " id="table_vw3_rcz_n4"> 
 <thead class="- topic/thead "> 
  <tr rowsep="1" class="- topic/row "> 
   <th class="- topic/entry entry" colspan="2"> Preference </th> 
   <th colname="3" class="- topic/entry entry"> Description </th> 
  </tr> 
 </thead>
 <tbody class="- topic/tbody "> 
  <tr rowsep="1" class="- topic/row "> 
   <td class="- topic/entry " colspan="2"> License Server Transport Certificate </td> 
   <td colname="3" class="- topic/entry "> The server transport certificate, issued by Adobe. This certificate is used to secure communications between the client and license server. The file must be located in the Resource Directory. </td> 
  </tr> 
  <tr rowsep="1" class="- topic/row "> 
   <td class="- topic/entry " colspan="2"> Enable HSM </td> 
   <td colname="3" class="- topic/entry "> Specifies whether certificates and credentials are stored on an HSM. If so, preferences related to certificates and credentials will be disabled, and the properties on the HSM tab must be specified. </td> 
  </tr> 
  <tr rowsep="1" class="- topic/row "> 
   <td class="- topic/entry " colspan="2"> Key Encryption Options </td> 
   <td colname="3" class="- topic/entry "> Specifies how the Content Encryption Key is encrypted at packaging time </td> 
  </tr> 
  <tr rowsep="1" class="- topic/row "> 
   <td colname="1" class="- topic/entry "></td> 
   <td colname="2" class="- topic/entry "> License Server Certificate </td> 
   <td colname="3" class="- topic/entry "> The License Server Certificate, issued by Adobe. The file must be located in the Resource Directory. The CEK is encrypted with the public key of the license server. Only holders of the license server private key may decrypt the CEK. </td> 
  </tr> 
  <tr rowsep="1" class="- topic/row "> 
   <td class="- topic/entry " colspan="2"> <p class="- topic/p ">Packager Credential </p> </td> 
   <td colname="3" class="- topic/entry "> The packager credential, issued by Adobe. This file is used to sign the metadata during packaging. </td> 
  </tr> 
  <tr rowsep="1" class="- topic/row "> 
   <td colname="1" class="- topic/entry "></td> 
   <td colname="2" class="- topic/entry "> File Name </td> 
   <td colname="3" class="- topic/entry ">The PKCS#12 (<span class="filepath"> .pfx</span>) file containing certificate and private key. The file must be located in the <span class="filepath"> Resource</span> Directory. </td> 
  </tr> 
  <tr rowsep="1" class="- topic/row "> 
   <td colname="1" class="- topic/entry "></td> 
   <td colname="2" class="- topic/entry "> File Password </td> 
   <td colname="3" class="- topic/entry ">Password for <span class="filepath"> .pfx</span> file </td> 
  </tr> 
  <tr rowsep="1" class="- topic/row "> 
   <td class="- topic/entry " colspan="2"> Global Watched Folder Properties </td> 
   <td colname="3" class="- topic/entry "> Specifies settings common to all Watched Folders configured on this server. </td> 
  </tr> 
  <tr rowsep="1" class="- topic/row "> 
   <td colname="1" class="- topic/entry "></td> 
   <td colname="2" class="- topic/entry "> Check Interval in Milliseconds </td> 
   <td colname="3" class="- topic/entry "> Specifies how often Watched Folders should check for new content to package. The server iterates through all the configured Watched Folders, then sleeps for this amount of time. </td> 
  </tr> 
  <tr rowsep="1" class="- topic/row "> 
   <td colname="1" class="- topic/entry "></td> 
   <td colname="2" class="- topic/entry "> Output File Name Suffix </td> 
   <td colname="3" class="- topic/entry ">Specifies a file extension to add to output files. For example, if <span class="filepath"> .out</span> is specified and the input file is <span class="filepath"> video.flv</span>, the output file would be <span class="filepath"> video.out.flv</span>. </td> 
  </tr> 
  <tr rowsep="1" class="- topic/row "> 
   <td colname="1" class="- topic/entry "></td> 
   <td colname="2" class="- topic/entry "> Backup Input Files </td> 
   <td colname="3" class="- topic/entry "> Specifies whether a copy of the original content should be saved. If this option is not selected, the original file will be deleted after packaging has been completed successfully. </td> 
  </tr> 
  <tr rowsep="1" class="- topic/row "> 
   <td colname="1" class="- topic/entry "></td> 
   <td colname="2" class="- topic/entry "> Input Backup Subfolder Name </td> 
   <td colname="3" class="- topic/entry "> If the Backup Input Files option is selected, specifies a folder where input files will be saved. This option specifies a folder name relative to the Watched Folder input directory. If the folder does not exist, it will be created during packaging. </td> 
  </tr> 
  <tr rowsep="0" class="- topic/row "> 
   <td colname="1" class="- topic/entry "></td> 
   <td colname="2" class="- topic/entry "> Overwrite Existing Output Files </td> 
   <td colname="3" class="- topic/entry "> Specifies whether the output file may be overwritten if a file already exists with the same name. If this option is not selected and the output file already exists, processing of the input file will be skipped. </td> 
  </tr> 
 </tbody> 
</table>


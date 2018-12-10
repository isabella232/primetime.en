---
seo-title: Configuration file properties
title: Configuration file properties
uuid: ad3d4914-c122-4369-96b9-490d2eb647ac
index: y
internal: n
snippet: y
---

# Configuration file properties{#configuration-file-properties}

Before running the License Generator, you need to specify values for the License Generator properties in the configuration file. 

>[!NOTE]
>
>For property names that include *n*, *n* represents an integer that starts with 1 and increases for each instance of the property.

<table frame="all" colsep="1" rowsep="1" class="+ topic/table adobe-d/table " id="table_qk1_rry_n4"> 
 <thead class="- topic/thead "> 
  <tr rowsep="1" class="- topic/row "> 
   <th colname="1" class="- topic/entry entry"> Property </th> 
   <th colname="2" class="- topic/entry entry"> Description </th> 
  </tr> 
 </thead>
 <tbody class="- topic/tbody "> 
  <tr rowsep="1" class="- topic/row "> 
   <td colname="1" class="- topic/entry "><span class="+ topic/ph pr-d/codeph codeph"> licensegen.minClientVersion</span> </td> 
   <td colname="2" class="- topic/entry "> <p>Sets the currently supported minimum client version. If you do not set this property, all versions are automatically supported by default. </p> <p>You can set this value to control how older clients respond to the license requirements that they do not support. Specify <span class="codeph"> x</span> (for Adobe Primetime DRM x.0) where <span class="codeph"> x</span> represents a major release number. </p> </td> 
  </tr> 
  <tr rowsep="1" class="- topic/row "> 
   <td colname="1" class="- topic/entry "><span class="+ topic/ph pr-d/codeph codeph"> licensegen.keyServerCert</span> </td> 
   <td colname="2" class="- topic/entry "> Key Server Certificate, which is an Adobe-issued License Server certificate that is used by the Key Server. This certificate is applied only if the metadata/DRM policy indicates that a Key Server is required for key delivery to iOS devices. </td> 
  </tr> 
  <tr rowsep="1" class="- topic/row "> 
   <td colname="1" class="- topic/entry "><span class="+ topic/ph pr-d/codeph codeph"> licensegen.sign.certfile</span> </td> 
   <td colname="2" class="- topic/entry "> The PKCS12 file that includes the License Server credentials for signing licenses. This property needs to refer to a .pfx file that includes a certificate and private key. </td> 
  </tr> 
  <tr rowsep="1" class="- topic/row "> 
   <td colname="1" class="- topic/entry "><span class="+ topic/ph pr-d/codeph codeph"> licensegen.sign.certpass</span> </td> 
   <td colname="2" class="- topic/entry ">The password that protects the file that you have specified with the <span class="+ topic/ph pr-d/codeph codeph"> licensegen.sign.certfile</span> option. </td> 
  </tr> 
  <tr rowsep="1" class="- topic/row "> 
   <td colname="1" class="- topic/entry "><span class="+ topic/ph pr-d/codeph codeph">licensegen.domainca.n</span> </td> 
   <td colname="2" class="- topic/entry "> <p>If you generate domain-bound licenses, you must specify one or more Domain CA certificates to indicate the domain authorities that the license issuer can trust. </p> <p>If the license recipient is a domain certificate, which was not issued by one of the specified Domain CAs, then a license cannot be generated. This property specifies a <span class="filepath"> .cer</span> file that includes the certificate in the PEM or the DER format. <span class="codeph">n</span> must increase monotonically, starting from 1. </p> </td> 
  </tr> 
  <tr rowsep="1" class="- topic/row "> 
   <td colname="1" class="- topic/entry "> 
    <lines>
     <span class="+ topic/ph pr-d/codeph codeph">licensegen.keys.asymmetric. licenseServerCredential.n</span>
    </lines> </td> 
   <td colname="2" class="- topic/entry "> <p class="- topic/p ">Optional PKCS12 file that includes additional License Server credentials for decrypting the CEK in the metadata and DRM policy. You can configure additional credentials if content has previously been packaged with a License Server certificate other than those credential that have been specified with <span class="codeph"> licensegen.sign.certfile</span>. This property needs to refer to a <span class="filepath"> .pfx</span> file that includes a certificate and private key. <span class="codeph">n</span> must increase monotonically, starting from 1. </p> </td> 
  </tr> 
  <tr rowsep="0" class="- topic/row "> 
   <td colname="1" class="- topic/entry "> 
    <lines>
     <span class="+ topic/ph pr-d/codeph codeph">licensegen.keys.asymmetric. licenseServerCredential.n.password</span>
    </lines> </td> 
   <td colname="2" class="- topic/entry "> <p>The password is applied to protect the file that you have specified with the<span class="+ topic/ph pr-d/codeph codeph"> licensegen.keys.asymmetric.licenseServerCredential.n</span> property. </p> </td> 
  </tr> 
 </tbody> 
</table>


---
description: The DRM Client errors are a subset of the TVSDK client-side errors. 
seo-description: The DRM Client errors are a subset of the TVSDK client-side errors. 
seo-title: DRM Client Error Message Reference
title: DRM Client Error Message Reference
---

# DRM Client Error Message Reference {#client-error-message-reference}

The DRM Client errors are a subset of the TVSDK client-side errors, with the DRM-related errors codes ranging from 3300 to 3399.

## Client errors {client-errors}

>[!Note]
>Primetime DRM was formerly called Adobe Access, and prior to that >was called Flash Access.

<table>
 <tbody>
  <tr>
    <th>Error Code</th>
    <th align="center">Mnemonic</th>
    <th align="center">Remedy</th>
  </tr>
  <tr>
  <td>3300</td>
      <td align="center">InvalidVoucher</td>
      <td>
      <ul>
        <li>What the distributor's software should do:
           <ul><li>If you are using Google Chrome, and you are in Incognito mode, and your Flash Player version is lower than 11.6, this error might occur. We recommend that the player check the browser's version number and advise the user to exit Incognito mode.</li>
           <li>Request the license again. If the request is successful, you do not need to log or escalate. If the request is unsuccessful, log the content that caused the error. subErrorId contains a line error if present.
</li></ul></li>
<li>What the distributor should do:
        <ul><li>If retries are unsuccessful on configurations other than Chrome with Flash less than version 11.6, a failure might have occurred in the packaging</li>
        <li>Check whether the issue is specific to certain content
        and repackage.</li></ul></li></ul>  
</td>
</tr>
</tbody>
</table>
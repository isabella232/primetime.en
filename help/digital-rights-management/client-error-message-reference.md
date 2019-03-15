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
>Primetime DRM was formerly called Adobe Access, and prior to that was called Flash Access.

<table>
  <tbody>
     <tr>
         <th>Error Code</th>
         <th>Mnemonic</th>
         <th>Remedy</th>
      </tr>
      <tr>
          <td>3300</td>
          <td>InvalidVoucher</td>
          <td>
              <ul>
                   <li>What the distributor's software should do:
                      <ul>
                          <li>If you are using Google Chrome, and you are in Incognito mode, and your Flash Player version is lower than 11.6, this error might occur. We recommend that the player check the browser's version number and advise the user to exit Incognito mode.</li>
                          <li>Request the license again. If the request is successful, you do not need to log or escalate. If the request is unsuccessful, log the content that caused the error. subErrorId contains a line error if present.</li>
                      </ul>
                    </li>
                    <li>What the distributor should do:
                       <ul>
                           <li>If retries are unsuccessful on configurations other than Chrome with Flash less than version 11.6, a failure might have occurred in the packaging</li>
                           <li>Check whether the issue is specific to certain content and repackage.</li>
                       </ul>
                    </li>
              </ul> 
            </td>
        </tr>  
    </tr>   
       <tr>
            <td>3301</td>
            <td>AuthenticationFailed</td>
            <td>The server failed to authenticate or authorize the client.
               <ul>
                        <li>The distributor’s software should take any action necessary to re-establish the user’s credentials or guide the user to acquire access to the content.</li>
                        <li>The distributor should confirm that its authorization and authentication mechanism is working correctly. If the distributors are not planning to use the authentication or authorization features, they should check whether the policy of the offending content requires authentication, and see Diagnosing policy / license discrepancies.</li>
                </ul>
        For more information about this error code, see <a href="https://forums.adobe.com/thread/1277149">DRM Error 3301 causes and resolution.</a>
            </td>
      </tr>    
    </tbody>
</table>
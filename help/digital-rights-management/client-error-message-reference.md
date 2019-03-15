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
      <tr>
            <td>3302</td>
            <td>RequireSSL</td>
            <td>For Primetime DRM 4.0 and above, this error is thrown on iOS when the remote key URL does not use HTTPS as the scheme. HTTPS is required.
          <ul>
              <li>If distributor is using a version older than Primetime DRM version 4, or at least version 4 but the platform is not iOS, the distributor's software should log the error. This error is thrown only on iOS</li>
              <li>If the distributor's software is at least Primetime DRM version 4, and the platform is iOS, distributors must change the remote key server URL that they are using to HTTPS. If they were only using HTTP, distributors might have to set up an HTTPS server. Otherwise, the distributors need to submit the logged information to Adobe and escalate the issue.</li>
          </ul>
      	    </td>
    </tr>
    <tr>
          <td>3303</td>
          <td>ContentExpired</td>
          <td>The content you are viewing has expired according to the rules set by the content provider. subErrorId contains a client-specific error or line error.
            <ul>
                <li>The distributor's software should attempt to reacquire a license from the server once to determine whether a new non-expired license is available. If no license is available or the license has expired, allow the user to acquire a new license, or inform the user that the content cannot be watched.</li>
            </ul>
 If the content has been packaged with a policy that has a lapsed expiration/end date, and the license server logs report a PolicyEvaluationException, state that the Policy End Date has lapsed (Server Error code 303). Check the server's log files to verify.

 If possible, customers should check the policy that they used during packaging to see whether it has expired. The Java command line tool is:

    java -jar libs/AdobePolicyManager.jar
    detail demo.pol
<ul>
          <li>The distributor should confirm whether license expiration dates are configured as intended.</li>
      </ul>
 For more information about this error code, see <a href="https://forums.adobe.com/thread/1300813">3303 (Content Expired) with AMS/FMS using a Live Stream.</a>
          </td>
      </tr>
      <tr>
          <td>3304</td>
          <td>AuthorizationFailed</td>
          <td>The current user is not authorized to view content. Login as a different user.
              For more information about this error code, see Error code 3301.
          </td>
      </tr>
      <tr>
        <td>3305</td>
        <td>ServerConnectionFailed</td>
        <td>The connection to the license or domain servers timed out, either due to network delay or the client being offline. NormallysubErrorId contains the HTTP return code.
            <ul>
                <li>The distributor's software should attempt a network connection to a known good server. If the attempt fails, prompt the user to reconnect to the network. If the attempt is successful, log it.</li>
                <li>The distributor should verify that any license and domain servers in use are online and visible from the client's network.</li>
            </ul>
     For more information about this error code, see <a href="https://forums.adobe.com/thread/1284947">DRM 3305 [ServerConnectionFailed] causes and resolution.</a>
         </td>
      </tr>
      <tr>
        <td>3306</td>
        <td>ClientUpdateRequired</td>
        <td>The current client cannot complete the requested action, but an updated client might be able to complete the request. This can have several causes:
          <ul>
              <li>A shared domain was used that is not available on this client. This is likely the case when playback works on Chrome, but not any other browser and vice versa.</li>
          </ul>
        <b>Note:</b>Chrome uses a different PHDS/PHLS key than the other browsers use.
          <ul>
            <li>The application is trying to add multiple DRMSessions when running on an iOS version that is earlier than 5.0.</li>
            <li>The metadata has a version of 3 or higher when only version 2 is supported.</li>
            <li>The distributor's software should alert the user and abort the operation. If the software has a way of determining whether an upgrade is available, direct the user to that upgrade in the appropriate manner for the platform.</li>
            <li>If the issue occurs because of a shared domain, the distributor will need to check with Adobe for an updated runtime or library. In the case of Flash runtime, the distributor can force the upgrade in their application directly. In the case of a library, the distributor will need to obtain an updated library, rebuild their application and deploy it to their users.</li>
          </ul>

       If the issue occurs because of multiple DRMSessions, the distributor will need to update their application to check the iOS version number prior to adding multiple DRMSessions. Or they can restrict distribution of their application to iOS version 5 and above.

      If the issue occurs because the metadata version is higher than version 2, the issue is probably corrupted metadata. They can try rebuilding the metadata and looking at the results. If they continue to see the problem, log the issue and escalate to Adobe.

For more information about this error code, see <a href="https://forums.adobe.com/thread/1266675">How to remedy a 3306 DRMErrorEvent Error code.</a>
          </td>
    </tr>
    <tr>
          <td>3307</td>
          <td>InternalFailure</td>
          <td>This generally represents a bug in Primetime DRM code and is unexpected, unless there's a known bug, as below.subErrorId contains a client-specific error or line error.
              <ul>
                    <li>If the browser is Chrome on Windows and Flash version is 11.6 (SWF version 19 or greater), the distributor's software should assume that the user pressed Deny on the infobar and treat the same as a 3368</li>
                    <li>If 3307 occurs when browser is not Chrome or Flash version is not 11.6, the distributor should escalate to Adobe.</li>
              </ul>
           <b>Note:</b> 3307:1107296344 (FailedToGetBrokerHandle) might happen with Chrome browser versions 24-28.
          </td>
        </tr>
    <tr>
            <td>3308</td>
            <td>WrongLicenseKey</td>
            <td>This error is thrown whenever the license being used contains the wrong key to decrypt the content. The subErrorIdcontains a client-specific error or line error. There seems to be only two ways of generating this error:
                <ul>
                        <li>The customer has modified the standard Adobe tooling for generating licenses (for example, the licenser server Java framework). In this case, the license contains a bad key which might not correspond to any content.</li>
                        <li>The customer has issued multiple licenses with the same license ID. In this case, there are multiple licenses that are available on the client that match the content metadata and the Primetime DRM code has selected the wrong one for use.</li>
                        <li>The distributor's software should attempt to reacquire the license from the server.</li>
                <ul>
                    <li>If no license is available or the license is expired, provide a workflow for the user to acquire a new license, or inform the user that the content cannot be watched, and log the issue.
                    If this was a domain bound content (for AIR), provide a way for the user to join the domain.</li>
                </ul>
                    <li>The distributor should:</li>
                <ul>
                    <li>Verify that they have not customized the license issuance portions of thePrimetime DRM License server.</li>
                    <li>Verify that they are issuing unique license IDs for all licenses</li>
                    <li>Escalate the issue with Adobe.</li>
              </ul>
              </ul>
            </td>
      </tr>
      <tr>
              <td>3309</td>
              <td>CorruptedAdditionalHeader</td>
              <td>This will occur if the header is larger than 65536 bytes.
                    <ul>
                            <li>The distributor's software should Log which piece of content caused the error.</li>
                            <li>The distributor should confirm that error is reproducible with specific pieces of content. Repackage broken content.</li>
                    </ul>
              </td>
      </tr>
      <tr>
              <td>3310</td>
              <td>AppIDMismatch</td>
              <td>Application is not white listed. Android, iOS, or Flash SWF.
                  subErrorId: 1000942; Error playing protected stream. FAXS error.
                  It is also possible that the client is reporting an empty string for pubID (app Publisher ID ).
                  <b>Android:</b>The Android application does not match the one in use. Bear in mind that the directory for the debug keystore in Android is often different than the directory for the release keystore.
                  <b>iOS:</b>See the "Whitelist your iOS application" in the TVSDK iOS guide.
              </td>
      </tr>
      <tr>
            <td>3312</td>
            <td>LicenseIntegrity</td>
            <td>Download the license from the server again.</td>
      </tr>
      <tr>
            <td>3313</td>
            <td>WriteMicrosafeFailed</td>
            <td>This issue occurs when the system cannot write to the file system. subErrorIdcontains a client-specific error or line error.

	    On Microsoft Windows, error 3313 might be thrown by Active X or NPAPI plug flash player when the encrypted content has a licenseID or a policyID that is too long. This is because of the maximum path length in Windows. (Pepper plugin doesn't have this problem).
<ul>  
                  <li>The distributor's software should prompt the user to confirm that their user directory is not locked nor on a volume that is full or locked.</li>
                  <li>If the distributor is using AIR, rather than Flash, the issue might be caused by a path length limitation. Distributors should shorten the name of their AIR application to something reasonable</li>
          </ul>
          </td>
      </tr>
      <tr>
          <td>3314</td>
          <td>CorruptedDRMMetadata</td>
          <td>This error often indicates that the content was packaged with test PKI certs, and the player is built with production PKI, or vice versa. The subErrorId contains a client-specific error or line error.
              <ul>
                    <li>The distributor's software should log which piece of content caused the error</li>
                    <li>The distributor should confirm that the error is reproducible with specific pieces of content.</li>
              </ul>
          You might have to repackage broken content.
            </td>
        </tr>
        <tr>
          <td>3315</td>
          <td>PermissionDenied</td>
          <td>There are known bugs in which this error code might be thrown when a 3305 is intended. For more information, see Error code 3305.
              A remote SWF loaded by AIR is not allowed to access Primetime DRM functionality. This error code can also be thrown if a security error occurs during network access. Examples include the destination server does not the client to connect by usingcrossdomain.xml, or the crossdomain.xmlis not reachable.
              For more information, see <a href="https://forums.adobe.com/thread/1266592"> DRM error 3315 possible root cause and resolution.</a>
          </td>
    </tr>
    <tr>
          <td>3317</td>
          <td>AAXS_LoadAdobeCPFailed</td>
          <td><b>Important:</b>This is a rare error and usually does not occur in a production environment.
              If the error does occur, you can do one of the following:
                <ul>
                      <li>If you are using AIR, reinstall AIR.</li>
                     <li>If you are using Flash Player, download the AdobeCP modules again.</li>
                </ul>
          </td>
      </tr>
      <tr>
          <td>3318</td>
          <td>IncompatibleAdobeCPVersion</td>
          <td><b>Important:</b>This is a rare error and usually does not occur in a production environment.
              If the error does occur, you can do one of the following:
              <ul>
                    <li>If you are using AIR, reinstall AIR.</li>
                    <li>If you are using Flash Player, download the AdobeCP modules again.</li>
              </ul>
          </td>
      </tr>
      <tr>
          <td>3319</td>
          <td>MissingAdobeCPGetAPI</td>
          <td><b>Important:</b>This is a rare error and usually does not occur in a production environment.
              If the error does occur, you can do one of the following:
                <ul>
                    <li>If you are using AIR, reinstall AIR.</li>
                    <li>If you are using Flash Player, download the AdobeCP (Windows 8)modules again or reinstall Flash Player.</li>
                </ul>
          </td>
      </tr>
      <tr>
          <td>3320</td>
          <td>HostFailed</td>
          <td><b>Important:</b>This is a rare error and usually does not occur in a production environment.
                 If the error does occur, you can do one of the following:
                <ul>
                      <li>If you are using AIR, reinstall AIR.</li>
                      <li>Download the AdobeCP and Flash Playeragain because either solution could be out of sync.</li>
                </ul>
        The application only needs to update Flash Player, which results in AdobeCP being downloaded again.
        </td>
      </tr>
      <tr>
          <td>3321</td>
          <td>I15nFailed</td>
          <td>The process of provisioning the client with keys failed. The subErrorId contains a client-specific, server-specific or line error.
                <ul>
                      <li>The distributor's software should retry the operation at least once.</li>
                </ul>
        If you are using Google Chrome on Windows, provide an explanation about how to allow plugin access that is not in a sandbox. For more
        information see <a href="https://helpx.adobe.com/adobe-access/kb/error-3321.html">Google Chrome's unsandbox access denied.</a>
                      <li>The distributor should complete one of the following tasks:
                <ul>
                      <li>If the error is consistent across platforms, you should escalate the issue with Adobe.</li>
                      <li>If the error is confined to Chrome on Windows, guide the user to allow unsandboxed plugin access.</li>
                      </li>
                </ul>
        Distributors should update their SWF to version 19 or later. For the Chrome-specific 3321 error, a 3368 error is thrown. Error 3368 can be handled more specifically by the distributor's software. This change was introduced in Chrome Stable channel version 26.0.1410.43.

  <b>Note:</b>Error 3321:1090519056 might happen with Flash Playerversions 11.1 to 11.6. We recommend that you upgrade to the latest Flash Player version.

For more information, see <a href="https://forums.adobe.com/thread/1277138"> DRM error 3321 Causes & Resolution.</a>
        </td>
    </tr>
    <tr>
          <td>3322</td>
          <td>DeviceBindingFailed</td>
          <td>The device does not appear to match the configuration that was present when initialized. subErrorId contains a client-specific or line error. 
          The distributor's software should complete one of the following tasks:
                <ul>
                      <li>If the device is not using Flash Player, and is using AIR, iOS, and so on, callDRMManager.resetDRMVouchers().</li>
                </ul>
If the issue occurs on iOS in a development phase, ask the developer to confirm whether the issue is observed when switching between builds that were downloaded from third-party, pre-release distribution systems (for example, HockeyApp) and a local build from Xcode. Attributes of a previous installation are not entirely overwritten when switching between a build distributed from HockeyApp and a build from Xcode. This situation might trigger the 3322 error.

To resolve this issue, the developer should remove the older build from the device before installing the new build.
                <ul>
                    <li>If the device is using Flash Player, and it is unusable from a 3322 or 3346 Error code, see the instructions from Adobe about how to programmatically reset your DRM license store on <a href="https://forums.adobe.com/message/5535907#5535907"> DRM Error 3322/3346/3368 in Chrome (Info-Bar Problems).</a></li>
                </ul>
This error is not expected to occur frequently. In corporate environments that uses roaming profiles, if a user was viewing content that is protected by DRM, the chances error 3322 occurring increases as the user logs in from different machines. If possible, distributor should try to get this information from user.
If the error occurs frequently, escalate to Adobe. You must notify Adobe whether resetting license store did (or did not) solve the problem and tell Adobe on which browsers the error is occurring.
For more information, see the following articles:
              <ul>
                  <li><a href="https://forums.adobe.com/message/5520902"> https://forums.adobe.com/message/5520902</a></li>
                  <li><a href="https://forums.adobe.com/message/5535911"> https://forums.adobe.com/message/5535911</a></li>
                  <li><a href="https://forums.adobe.com/message/5748618"> https://forums.adobe.com/message/5748618</a></li>
                  <li><a href="https://forums.adobe.com/message/6061165"> https://forums.adobe.com/message/6061165</a></li>
              </ul>
        </td>
    </tr>
    </tbody>
</table>
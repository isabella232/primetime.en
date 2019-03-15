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



<div>
    <table border="1" cellspacing="0" cellpadding="0">
        <tbody>
            <tr>
                <td width="50" valign="top">
                    <p>
                        <strong>Error code</strong>
                    </p>
                </td>
                <td width="154" valign="top">
                    <p>
                        <strong>Mnemonic</strong>
                    </p>
                </td>
                <td width="456" valign="top">
                    <p>
                        <strong>Remedy</strong>
                    </p>
                </td>
            </tr>
            <tr>
                <td width="50" valign="top">
                    <p align="center">
                        3300
                    </p>
                </td>
                <td width="154" valign="top">
                    <p>
                        InvalidVoucher
                    </p>
                </td>
                <td width="456" valign="top">
                    <ul>
                        <li>
                            What the distributor's software should do:
                        </li>
                    </ul>
                    <p>
                        · If you are using Google Chrome, and you are in
                        Incognito mode, and your Flash Player version is lower
                        than 11.6, this error might occur. We recommend that
                        the player check the browser's version number and
                        advise the user to exit Incognito mode.
                    </p>
                    <p>
                        · Request the license again. If the request is
                        successful, you do not need to log or escalate. If the
                        request is unsuccessful, log the content that caused
                        the
                    </p>
                    <p>
                        error. subErrorId contains a line error if present.
                    </p>
                    <ul>
                        <li>
                            What the distributor should do:
                        </li>
                    </ul>
                    <p>
                        · If retries are unsuccessful on configurations other
                        than Chrome with Flash less than version 11.6, a
                        failure might have occurred in the packaging.
                    </p>
                    <p>
                        · Check whether the issue is specific to certain
                        content and repackage.
                    </p>
                </td>
            </tr>
            <tr>
                <td width="50" valign="top">
                    <p align="center">
                        3301
                    </p>
                </td>
                <td width="154" valign="top">
                    <p>
                        AuthenticationFailed
                    </p>
                </td>
                <td width="456" valign="top">
                    <p>
                        The server failed to authenticate or authorize the
                        client.
                    </p>
                    <p>
                        · The distributor’s software should take any action
                        necessary to re-establish the user’s credentials or
                        guide the user to acquire access to the content.
                    </p>
                    <p>
                        · The distributor should confirm that its authorization
                        and authentication mechanism is working correctly. If
                        the distributors are not planning to use the
                        authentication or authorization features, they should
                        check whether the policy of the offending content requires authentication, and see Diagnosing policy / licence discrepancies.
                </p>
                <p>
                    For more information about this error code, see
                    <u>
                        <a href="https://forums.adobe.com/thread/1277149">
                            DRM Error 3301 causes
                        </a>
                    </u>
                    <u>
                        <a href="https://forums.adobe.com/thread/1277149">
                            and resolution<u>.</u>
                        </a>
                    </u>
                </p>
            </td>
        </tr>
    </tbody>
</table>
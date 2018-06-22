---
description: You can set up the Reference Implementation to use Adobe Analytics reporting.
seo-description: You can set up the Reference Implementation to use Adobe Analytics reporting.
seo-title: Configure Adobe Analytics Reporting
title: Configure Adobe Analytics Reporting
---

# Configure Adobe Analytics Reporting

The Reference Implementation is configured to send  event data to Adobe Analytics using the Adobe Mobile Library bundled within the Primetime SDK. To enable and use the event data sent from the application, you must first create an Adobe Analytics account. Once the account is created:
1. Configure the application with your account information; and
1. Create processing rules to customize how the event data is displayed within your reports.
The table below presents the data sent to Adobe Analytics:

<table id="table_qys_x25_xp"> 
 <tgroup cols="3"> 
  <tbody> 
   <tr> 
    <td> Action Name </td> 
    <td> <span class="codeph"> a.media.pass.event.MvpdSelection </span> </td> 
    <td> The user selected a Multi-channel Video Programming Distirbutor (MVPD) in a selection dialog </td> 
   </tr> 
   <tr> 
    <td> Context Data </td> 
    <td> <span class="codeph"> a.media.pass.MvpdId (String) </span> </td> 
    <td> The user-selected MVPD </td> 
   </tr> 
   <tr> 
    <td></td> 
    <td> <span class="codeph"> a.media.pass.ClientType </span> </td> 
    <td> (String) The client type as either "flash", "html5", "ios", or "android" </td> 
   </tr> 
   <tr> 
    <td></td> 
    <td></td> 
    <td></td> 
   </tr> 
   <tr> 
    <td> Action Name </td> 
    <td> <span class="codeph"> a.media.pass.event.AuthenticationDetection </span> </td> 
    <td> An Authentication workflow completed </td> 
   </tr> 
   <tr> 
    <td> Context Data </td> 
    <td> <span class="codeph"> a.media.pass.Successful </span> </td> 
    <td> (Boolean) Whether the token request was successful, true or false </td> 
   </tr> 
   <tr> 
    <td></td> 
    <td> <span class="codeph"> a.media.pass.MvpdId </span> </td> 
    <td> (String) The user-selected MVPD </td> 
   </tr> 
   <tr> 
    <td></td> 
    <td> <span class="codeph"> a.media.pass.Guid </span> </td> 
    <td> (String) A tracking ID </td> 
   </tr> 
   <tr> 
    <td></td> 
    <td> <span class="codeph"> a.media.pass.Cached </span> </td> 
    <td> (Boolean) Token already in cache, true or false </td> 
   </tr> 
   <tr> 
    <td></td> 
    <td> <span class="codeph"> a.media.pass.ClientType </span> </td> 
    <td> (String) The client type as either "flash", "html5", "ios", or "android" </td> 
   </tr> 
   <tr> 
    <td></td> 
    <td></td> 
    <td></td> 
   </tr> 
   <tr> 
    <td> Action Name </td> 
    <td> <span class="codeph"> a.media.pass.event.AuthorizationDetection </span> </td> 
    <td> An Authorization workflow completed </td> 
   </tr> 
   <tr> 
    <td> Context Data </td> 
    <td> <span class="codeph"> a.media.pass.Successful </span> </td> 
    <td> (Boolean) Whether the token request was successful, true or false </td> 
   </tr> 
   <tr> 
    <td></td> 
    <td> <span class="codeph"> a.media.pass.MvpdId </span> </td> 
    <td> (String) The user selected MVPD </td> 
   </tr> 
   <tr> 
    <td></td> 
    <td> <span class="codeph"> a.media.pass.Guid </span> </td> 
    <td> (String) A tracking ID </td> 
   </tr> 
   <tr> 
    <td></td> 
    <td> <span class="codeph"> a.media.pass.Cached </span> </td> 
    <td> (Boolean) Token already in cache, true or false </td> 
   </tr> 
   <tr> 
    <td></td> 
    <td> <span class="codeph"> a.media.pass.Error </span> </td> 
    <td> (String) The error if the authorization attempt failed </td> 
   </tr> 
   <tr> 
    <td></td> 
    <td> <span class="codeph"> a.media.pass.ErrorDetails </span> </td> 
    <td> (String) Further error details </td> 
   </tr> 
   <tr> 
    <td></td> 
    <td> <span class="codeph"> a.media.pass.ClientType </span> </td> 
    <td> (String) The client type as either "flash", "html5", "ios", or "android" </td> 
   </tr> 
  </tbody> 
 </tgroup> 
</table>

>1. Configure the application for use with Adobe Marketing Cloud.
>   To enable sending Primetime data to Adobe Analytics, an `filepath  ADBMobileConfig.json` configuration file must be added to the Reference Implementation at compile time. Note that this is exactly the same configuration file used by the Primetime SDK to send Video Analytics data to the Marketing Cloud. Please consult the [ Adobe Marketing Cloud documentation ](http://microsite.omniture.com/t2/help/en_US/reference/) for more information on configuring an application with your Adobe Analytics account.
>   
>1. Create processing rules.
>   The event data sent by the Reference Implementation will not automatically appear in your analytics reports. You must first make use of the data by creating processing rules. Please consult the [ Adobe Analytics documentation on creating processing rules ](http://microsite.omniture.com/t2/help/en_US/reference/processing_rules.html).
>   
>   

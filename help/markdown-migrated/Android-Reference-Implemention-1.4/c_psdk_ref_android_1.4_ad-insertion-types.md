---
description: The currently provides built-in ad provider metadata support for ads, direct ad breaks, and custom ad markers.
seo-description: The currently provides built-in ad provider metadata support for ads, direct ad breaks, and custom ad markers.
seo-title: Ad insertion types
title: Ad insertion types
---

# Ad insertion types

It supports the following types of ad insertion workflows for VOD and live/linear content.

<table id="table_1C3A659BDDB7453CA953A103045FCA01"> 
 <tgroup cols="3">
  <colspec colnum="1" colname="col1" colwidth="1.42*" />
  <colspec colnum="2" colname="col2" colwidth="1.00*" />
  <colspec colnum="3" colname="col3" colwidth="4.40*" />
  <thead> 
   <tr> 
    <th colname="col1" class="entry">Insertion type</th> 
    <th colname="col2" class="entry">Supported in...</th> 
    <th colname="col3" class="entry">Description</th> 
   </tr>
  </thead> 
  <tbody> 
   <tr> 
    <td colname="col1">
     <ph conref="../../phrase_library_ref_impl.xml#c_psdk_phrase-library/auditude-name-long">
      Phrase
     </ph> ads </td> 
    <td colname="col2">VOD <p>Live</p> <p>Linear</p> </td> 
    <td colname="col3">The reference implementation provides <span class="codeph">AuditudeMetadata</span> information to connect to the server for 
     <ph conref="../../phrase_library_ref_impl.xml#c_psdk_phrase-library/auditude-name">
      Phrase
     </ph> (previously known as 
     <ph conref="../../phrase_library_ref_impl.xml#c_psdk_phrase-library/auditude-name-previously-known-as">
      Phrase
     </ph>), based on the information provided in the <a href="../reference/r_psdk_ref_json-pt-ads.xml" format="dita" scope="peer">Primetime ads portion</a> of the <a href="../reference/r_psdk_ref_example-json-feed-format.xml" format="dita" scope="peer">JSON configuration file</a>. </td> 
   </tr> 
   <tr> 
    <td colname="col1">Direct ad breaks</td> 
    <td colname="col2">VOD</td> 
    <td colname="col3">You must provide ad URLs in the input JSON file. When the 
     <ph conref="../../phrase_library_ref_impl.xml#c_psdk_phrase-library/primetime-sdk-name" /> attempts to resolve an ad, it calls the direct ad break resolver and resolves the ads based on the <a href="../reference/r_psdk_ref_json-direct-ad-breaks.xml" format="dita" scope="peer">direct ad breaks information</a> provided in the <a href="../reference/r_psdk_ref_example-json-feed-format.xml" format="dita" scope="peer">JSON configuration file</a>. </td> 
   </tr> 
   <tr> 
    <td colname="col1">Custom ad markers</td> 
    <td colname="col2">VOD</td> 
    <td colname="col3">Custom ad markers are useful when the video stream contains both main content and ads but does not include information related to the ad positions and timing. If the ad positioning information is obtained in another way, for example, through an external CMS, you can define custom ad markers and pass them to the player timeline. <p>To set up a player for ad insertion, you need to pass ad metadata in the<a href="../reference/r_psdk_ref_json-custom-ad-markers.xml" format="dita" scope="peer">custom ad metadata section</a> of the <a href="../reference/r_psdk_ref_example-json-feed-format.xml" format="xml" scope="peer">JSON configuration file</a>, which has a supporting ad provider implementation in the reference implementation. </p> </td> 
   </tr> 
  </tbody> 
 </tgroup> 
</table>


---
description: FYI, this topic doesn't appear to be used anywhere at this time (April 2015). That's good because it's incorrect, outdated, doesn't use items from the phrase library when it should, etc. Not going to fix it because it's not used. -ellen
seo-description: FYI, this topic doesn't appear to be used anywhere at this time (April 2015). That's good because it's incorrect, outdated, doesn't use items from the phrase library when it should, etc. Not going to fix it because it's not used. -ellen
seo-title: MBR configuration details
title: MBR configuration details
---

# MBR configuration details

There is only one public API: setABRParameters()

<table id="table_9426F6E338CB456A98BE6BC51717AE34"> 
 <tgroup cols="2">
  <colspec colnum="1" colname="col1" colwidth="1.00*" />
  <colspec colnum="2" colname="col2" colwidth="3.19*" /> 
  <tbody> 
   <tr> 
    <td colname="col1">getABRInitialBitRate() </td> 
    <td colname="col2">Returns an integer value that represents the byte-per-second profile. </td> 
   </tr> 
   <tr> 
    <td colname="col1">getABRMinBitRate() </td> 
    <td colname="col2">Returns an integer value that represents the byte-per-second profile. </td> 
   </tr> 
   <tr> 
    <td colname="col1">getABRMaxBitRate() </td> 
    <td colname="col2">Returns an integer value that represents the byte-per-second profile. </td> 
   </tr> 
   <tr> 
    <td colname="col1"><a href="http://help.adobe.com/en_US/primetime/api/psdk/javadoc/com/adobe/mediacore/ABRControlParameters.html#getABRPolicy()" format="html" scope="external">getABRPolicy()</a> </td> 
    <td colname="col2">Returns the ABRPolicy enum: ABR_AGGRESSIVE, ABR_CONSERVATIVE and ABR_MODERATE . </td> 
   </tr> 
  </tbody> 
 </tgroup> 
</table>

To return the parameters required for MBR processing, you need to implement the following functions from IPlaybackConfig:


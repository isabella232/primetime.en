---
description: Browser TVSDK supports a number of HLS features that you can implement to add functionality to your video applications.
seo-description: Browser TVSDK supports a number of HLS features that you can implement to add functionality to your video applications.
seo-title: Supported HLS features
title: Supported HLS features
uuid: 033d81f8-cea4-4687-b2fb-1524d9164d39
index: y
internal: n
snippet: y
---

# Supported HLS features{#supported-hls-features}

Browser TVSDK supports a number of HLS features that you can implement to add functionality to your video applications.

* [HLS Core playback](../../../browser-tvsdk-2.4/c-psdk-browser-2.4-introduction/new-features/c-psdk-browser-tvsdk-2.4-new-features-b-hls.md#table_0524BD3F2CD1499D95BD4A9D4F451C1B) 
* [HLS Advanced playback features](../../../browser-tvsdk-2.4/c-psdk-browser-2.4-introduction/new-features/c-psdk-browser-tvsdk-2.4-new-features-b-hls.md#table_EEF70EB81AB544519E71FD8CC306CC00) 
* [HLS Content protection features](../../../browser-tvsdk-2.4/c-psdk-browser-2.4-introduction/new-features/c-psdk-browser-tvsdk-2.4-new-features-b-hls.md#table_613AF7D254424965AE11C5189D9A7BA8) 
* [HLS Core ad insertion features](../../../browser-tvsdk-2.4/c-psdk-browser-2.4-introduction/new-features/c-psdk-browser-tvsdk-2.4-new-features-b-hls.md#table_8889329FC60F4B68BA6E898B632AB59C) 
* [HLS Advanced ad insertion features](../../../browser-tvsdk-2.4/c-psdk-browser-2.4-introduction/new-features/c-psdk-browser-tvsdk-2.4-new-features-b-hls.md#table_7F018C879D254291A6803C2F11CEC589) 
* [HLS Integrations](../../../browser-tvsdk-2.4/c-psdk-browser-2.4-introduction/new-features/c-psdk-browser-tvsdk-2.4-new-features-b-hls.md#table_FFFBDCBA719D4BABBD65DC2F7AC34A5A)

>[!TIP]
>
>In the feature matrix tables below,  ![](assets/supported15.png)>
>means that the feature is supported in the current release.

>[!TIP]
>
>In the Safari column "Platform Limitation" means that the use case is not supported because that platform does not allow implementation of support for it. In the case of a insertion, use SSAI. If there are playback limitations important to you, force fallback to Flash on Safari until the platform supports the ad insertion use case.

<a id="section_9FB9193D5763448CB228B96164661738"></a>

The following features are supported: 

<!-- 

Removed Nielsen row 
<table id="table_D9E2D82992554905A0A551CC71AFA189"> 
 <title>HLS integrations</title> 
 <tgroup cols="6"> 
  <colspec colnum="1" colname="col1" colwidth="*" /> 
  <colspec colnum="2" colname="col2" colwidth="*" /> 
  <colspec colnum="3" colname="col3" colwidth="*" /> 
  <colspec colnum="4" colname="col4" colwidth="*" /> 
  <colspec colnum="5" colname="col5" colwidth="*" /> 
  <colspec colnum="6" colname="col7" colwidth="*" /> 
  <thead> 
   <tr> 
    <th colname="col1" morerows="1" class="entry"> Category </th> 
    <th colname="col2" morerows="1" class="entry"> Content type </th> 
    <th colname="col3" morerows="1" class="entry"> Feature </th> 
    <th colname="col4" morerows="1" align="center" class="entry"> Flash </th> 
    <th align="center" namest="col5" nameend="col7" class="entry"> HTML5 </th> 
   </tr> 
   <tr> 
    <th colname="col5" align="center" class="entry"> FF, IE, Chrome, Android Chrome </th> 
    <th colname="col7" align="center" class="entry"> Safari, iOS Safari </th> 
   </tr> 
  </thead> 
  <tbody> 
   <tr> 
    <td colname="col1"> Integrations </td> 
    <td colname="col2"> VOD + Live </td> 
    <td colname="col3"> Adobe Analytics VHL integration </td> 
    <td colname="col4" valign="middle" align="center"><img href="assets/supported15.png" id="image_8FD1AD4F010A4157BE77E472B2272EDB" /> </td> 
    <td colname="col5" valign="middle" align="center"><img href="assets/supported15.png" id="image_1EEB0C1645DF42CBAB84351EAA50820F" /> </td> 
    <td colname="col7" valign="middle" align="center"><img href="assets/supported15.png" id="image_0E7E89334A0E477AB10C752335090FFC" /> </td> 
   </tr> 
   <tr> 
    <td colname="col1"> Integrations </td> 
    <td colname="col2"> VOD + Live </td> 
    <td colname="col3"> Nielsen support </td> 
    <td colname="col4" valign="middle" align="center"><img href="assets/supported15.png" id="image_545ADE0E897045FAA032C61D8F1497CC" /> </td> 
    <td colname="col5" valign="middle" align="center"><img href="assets/supported15.png" id="image_31BAE1FE2A564ED89E5FA1365A4B6F62" /> </td> 
    <td colname="col7" valign="middle" align="center"><img href="assets/supported15.png" id="image_9C2CA8AACFCE47689CDA8F3CC3499E23" /> </td> 
   </tr> 
  </tbody> 
 </tgroup> 
</table>

 -->

#### HLS integrations
<table id="table_FFFBDCBA719D4BABBD65DC2F7AC34A5A">  
 <thead> 
  <tr> 
   <th colname="col1" morerows="1" class="entry"> Category </th> 
   <th colname="col2" morerows="1" class="entry"> Content type </th> 
   <th colname="col3" morerows="1" class="entry"> Feature </th> 
   <th colname="col4" morerows="1" align="center" class="entry"> Flash </th> 
   <th align="center" class="entry" colspan="2"> HTML5 </th> 
  </tr> 
  <tr> 
   <th colname="col5" align="center" class="entry"> FF, IE, Chrome, Android Chrome </th> 
   <th colname="col7" align="center" class="entry"> Safari, iOS Safari </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Integrations </td> 
   <td colname="col2"> VOD + Live </td> 
   <td colname="col3"> Adobe Analytics VHL integration </td> 
   <td colname="col4" valign="middle" align="center"><img href="assets/supported15.png" id="image_B44D2B6DA65D4D88871EE7A1598A309E" /> </td> 
   <td colname="col5" valign="middle" align="center"><img href="assets/supported15.png" id="image_DFC9D920A84E40568AC703A46084B461" /> </td> 
   <td colname="col7" valign="middle" align="center"><img href="assets/supported15.png" id="image_5818C39DDC734CC1B6FCD00797A16D95" /> </td> 
  </tr> 
 </tbody> 
</table>

#### HLS advanced ad insertion features (CSAI)
<table id="table_7F018C879D254291A6803C2F11CEC589">  
 <thead> 
  <tr> 
   <th colname="col1" morerows="1" class="entry"> Category </th> 
   <th colname="col2" morerows="1" class="entry"> Content type </th> 
   <th colname="col3" morerows="1" class="entry"> Feature </th> 
   <th colname="col4" morerows="1" align="center" class="entry"> Flash </th> 
   <th align="center" class="entry" colspan="2"> HTML5 </th> 
  </tr> 
  <tr> 
   <th colname="col5" align="center" class="entry"> FF, IE, Chrome, Android Chrome </th> 
   <th colname="col7" align="center" class="entry"> Safari, iOS Safari </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Ad Insertion </td> 
   <td colname="col2"> VOD </td> 
   <td colname="col3"> Ad only </td> 
   <td colname="col4" align="center" valign="middle"> Not Supported </td> 
   <td colname="col5" valign="middle" align="center"><img href="assets/supported15.png" id="image_801336645D604CBB97911C38E0527D9E" /> </td> 
   <td colname="col7" valign="middle" align="center"><img href="assets/supported15.png" id="image_2E4FA56363804638B026B09B014D6128" /> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Ad Insertion </td> 
   <td colname="col2"> VOD + Live </td> 
   <td colname="col3"> Targeting parameters </td> 
   <td colname="col4" align="center" valign="middle"><img href="assets/supported15.png" id="image_D10067724C76424699E049D8ACC51FDA" /> </td> 
   <td colname="col5" valign="middle" align="center"><img href="assets/supported15.png" id="image_3D4B01EE2614436085A9AA125F230B46" /> </td> 
   <td colname="col7" valign="middle" align="center"><img href="assets/supported15.png" id="image_5BD621FED497413DB69DF8579D26CA57" /> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Ad Insertion </td> 
   <td colname="col2"> VOD + Live </td> 
   <td colname="col3"> Custom ad policy </td> 
   <td colname="col4" valign="middle" align="center"><img href="assets/supported15.png" id="image_ECB79B2987AE420CAA69E1EAF10B3CB9" /> </td> 
   <td colname="col5" valign="middle" align="center"><img href="assets/supported15.png" id="image_45A45F95799149A189B508E8059A144B" /> </td> 
   <td colname="col7" valign="middle" align="center"> Platform Limitation </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Ad Insertion </td> 
   <td colname="col2"> VOD + Live </td> 
   <td colname="col3"> Lazy ad loading </td> 
   <td colname="col4" valign="middle" align="center"><img href="assets/supported15.png" id="image_FB5874DC0E1C464F8DADCCEC07A21372" /> </td> 
   <td colname="col5" valign="middle" align="center"> Not Supported </td> 
   <td colname="col7" valign="middle" align="center"> Platform Limitation </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Ad Insertion </td> 
   <td colname="col2"> VOD </td> 
   <td colname="col3"> Companion ads, Banner ads, and Clickable ads </td> 
   <td colname="col4" valign="middle" align="center"><img href="assets/supported15.png" id="image_6B854827663D4B5EAA33D6748C095CF8" /> </td> 
   <td colname="col5" valign="middle" align="center"><img href="assets/supported15.png" id="image_F5635D29BB514250B136F8B065FC46F6" /> </td> 
   <td colname="col7" valign="middle" align="center"><img href="assets/supported15.png" id="image_9D3D3D6C0DA6495F8530759364A2BC8D" /> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Ad Insertion </td> 
   <td colname="col2"> VOD </td> 
   <td colname="col3"> VPAID 2.0 </td> 
   <td colname="col4" valign="middle" align="center"> SWF </td> 
   <td colname="col5" valign="middle" align="center"> JavaScript </td> 
   <td colname="col7" valign="middle" align="center"> JavaScript </td> 
  </tr> 
 </tbody> 
</table>

#### HLS core ad insertion features (CSAI)
<table id="table_8889329FC60F4B68BA6E898B632AB59C">  
 <thead> 
  <tr> 
   <th colname="col1" morerows="1" class="entry"> Category </th> 
   <th colname="col2" morerows="1" class="entry"> Content type </th> 
   <th colname="col3" morerows="1" class="entry"> Feature </th> 
   <th colname="col4" morerows="1" align="center" class="entry"> Flash </th> 
   <th align="center" class="entry" colspan="2"> HTML5 </th> 
  </tr> 
  <tr> 
   <th colname="col5" align="center" class="entry"> FF, IE, Chrome, Android Chrome </th> 
   <th colname="col7" align="center" class="entry"> Safari, iOS Safari </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Ad Insertion </td> 
   <td colname="col2"> VOD + Live </td> 
   <td colname="col3"> Pre-roll </td> 
   <td colname="col4" align="center" valign="middle"><img href="assets/supported15.png" id="image_9AACEEEC343F4FEF852E7932EE4BDBAE" /> </td> 
   <td colname="col5" align="center" valign="middle"><img href="assets/supported15.png" id="image_5E10DAB3A2724E56B0FBB7C169B27515" /> </td> 
   <td colname="col7" align="center" valign="middle"><img href="assets/supported15.png" id="image_FF496D7CE14746CBB83D5E6C76824810" /> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Ad Insertion </td> 
   <td colname="col2"> VOD + Live </td> 
   <td colname="col3"> Mid-roll </td> 
   <td colname="col4" align="center" valign="middle"><img href="assets/supported15.png" id="image_C47A96C2696F4B088350E3FAD3289864" /> </td> 
   <td colname="col5" align="center" valign="middle"><img href="assets/supported15.png" id="image_D2F43960AAEE43CE918398FDED91CC3B" /> </td> 
   <td colname="col7" align="center" valign="middle"> Platform Limitation </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Ad Insertion </td> 
   <td colname="col2"> VOD + Live </td> 
   <td colname="col3"> Post-roll </td> 
   <td colname="col4" align="center" valign="middle"> VOD only </td> 
   <td colname="col5" align="center" valign="middle"> VOD only </td> 
   <td colname="col7" align="center" valign="middle"> VOD only </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Ad Insertion </td> 
   <td colname="col2"> FER VOD </td> 
   <td colname="col3"> Ad resolution and Behaviors </td> 
   <td colname="col4" align="center" valign="middle"><img href="assets/supported15.png" id="image_50B39029B40249E5B10A055A67FF8009" /> </td> 
   <td colname="col5" align="center" valign="middle"><img href="assets/supported15.png" id="image_B6F965BAA6984F6181B0F79EA372B63B" /> </td> 
   <td colname="col7" align="center" valign="middle"> Platform Limitation </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Ad Insertion </td> 
   <td colname="col2"> VOD + Live </td> 
   <td colname="col3"> Default ad policy </td> 
   <td colname="col4" align="center" valign="middle"><img href="assets/supported15.png" id="image_F2392134D65149C1855547103705D7AA" /> </td> 
   <td colname="col5" align="center" valign="middle"><img href="assets/supported15.png" id="image_08C6BF8CA5DD429EAE36548CBAEA0BE2" /> </td> 
   <td colname="col7" align="center" valign="middle"> Platform Limitation </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Ad Insertion </td> 
   <td colname="col2"> VOD + Live </td> 
   <td colname="col3"> VAST 2.0/3.0 </td> 
   <td colname="col4" align="center" valign="middle"><img href="assets/supported15.png" id="image_3CC1EC05EDE346FAAE410CFE85FBEE9D" /> </td> 
   <td colname="col5" align="center" valign="middle"><img href="assets/supported15.png" id="image_376FEED608D74999B54DAD5DF6E76783" /> </td> 
   <td colname="col7" align="center" valign="middle"><img href="assets/supported15.png" id="image_556C470A74EB4002A84A4CA69A32669E" /> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Ad Insertion </td> 
   <td colname="col2"> VOD + Live </td> 
   <td colname="col3"> VMAP 1.0 </td> 
   <td colname="col4" align="center" valign="middle"><img href="assets/supported15.png" id="image_BE7ACBA0EB7841158360F6EA9E2B8BB1" /> </td> 
   <td colname="col5" align="center" valign="middle"><img href="assets/supported15.png" id="image_096B55A6D61844FE9818650FBB6F3275" /> </td> 
   <td colname="col7" align="center" valign="middle"><img href="assets/supported15.png" id="image_892698FFA2CA4EE18FBD027A759FE6A0" /> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Ad Insertion </td> 
   <td colname="col2"> VOD + Live </td> 
   <td colname="col3"> CRS v3.1 </td> 
   <td colname="col4" align="center" valign="middle"><img href="assets/supported15.png" id="image_85561023E50343B98E6E6C2B2074C913" /> </td> 
   <td colname="col5" align="center" valign="middle"><img href="assets/supported15.png" id="image_7A2C776CB9274AF7AD123027B2FA2A55" /> </td> 
   <td colname="col7" align="center" valign="middle"><img href="assets/supported15.png" id="image_D794D76DADE747A9BC839B37E32ECBAD" /> </td> 
  </tr> 
 </tbody> 
</table>

#### HLS content protection features
<table id="table_613AF7D254424965AE11C5189D9A7BA8">  
 <thead> 
  <tr> 
   <th colname="col1" morerows="1" class="entry"> Category </th> 
   <th colname="col2" morerows="1" class="entry"> Content type </th> 
   <th colname="col3" morerows="1" class="entry"> Feature </th> 
   <th colname="col4" morerows="1" align="center" class="entry"> Flash </th> 
   <th align="center" class="entry" colspan="2"> HTML5 </th> 
  </tr> 
  <tr> 
   <th colname="col5" align="center" class="entry"> FF, IE, Chrome, Android Chrome </th> 
   <th colname="col7" align="center" class="entry"> Safari, iOS Safari </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Content Protection </td> 
   <td colname="col2"> VOD + Live </td> 
   <td colname="col3"> AES-128 </td> 
   <td colname="col4" align="center" valign="middle"><img href="assets/supported15.png" id="image_D77A174E4686437A8D6B1F8FD80D3159" /> </td> 
   <td colname="col5" align="center" valign="middle"><img href="assets/supported15.png" id="image_7DFAE4665A2A4DF0B08E05FD2F32A4F0" /> </td> 
   <td colname="col7" align="center" valign="middle"><img href="assets/supported15.png" id="image_AE67505BF11041F29C535F37EF94BF3F" /> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Content Protection </td> 
   <td colname="col2"> VOD + Live </td> 
   <td colname="col3"> Sample-AES </td> 
   <td colname="col4" align="center" valign="middle"><img href="assets/supported15.png" id="image_8C9A5B0D652240CBA58B4CD6839A0D29" /> </td> 
   <td colname="col5" align="center" valign="middle"><img href="assets/supported15.png" id="image_3EA74DF02D504DD6A7804811B3E888F9" /> </td> 
   <td colname="col7" align="center" valign="middle"><img href="assets/supported15.png" id="image_B248BBE6A312422BB9DAE9D5774B4C58" /> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Content Protection </td> 
   <td colname="col2"> VOD </td> 
   <td colname="col3"> DRM </td> 
   <td colname="col4" valign="middle" align="center"> Adobe Access </td> 
   <td colname="col5" align="center" valign="middle"> Not Supported </td> 
   <td colname="col7" valign="middle" align="center"> FairPlay </td> 
  </tr> 
 </tbody> 
</table>

#### HLS advanced playback features
<table id="table_EEF70EB81AB544519E71FD8CC306CC00">  
 <thead> 
  <tr> 
   <th colname="col1" morerows="1" class="entry"> Category </th> 
   <th colname="col2" morerows="1" class="entry"> Content type </th> 
   <th colname="col3" morerows="1" class="entry"> Feature </th> 
   <th colname="col4" morerows="1" align="center" class="entry"> Flash </th> 
   <th align="center" class="entry" colspan="2"> HTML5 </th> 
  </tr> 
  <tr> 
   <th colname="col5" align="center" class="entry"> FF, IE, Chrome, Android Chrome </th> 
   <th colname="col7" align="center" class="entry"> Safari, iOS Safari </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Playback </td> 
   <td colname="col2"> VOD </td> 
   <td colname="col3"> Playback at offset </td> 
   <td colname="col4" align="center" valign="middle"><img href="assets/supported15.png" id="image_9B2DF9C6EB144409B4B944A18C8B3C16" /> </td> 
   <td colname="col5" align="center" valign="middle"><img href="assets/supported15.png" id="image_39D471D0546A4029A89D61C2B191C7F8" /> </td> 
   <td colname="col7" align="center" valign="middle"><img href="assets/supported15.png" id="image_983E739BB3A74EEEB67231A51797816E" /> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Playback </td> 
   <td colname="col2"> VOD </td> 
   <td colname="col3"> Audio only playback </td> 
   <td colname="col4" align="center" valign="middle"><img href="assets/supported15.png" id="image_2631277023D145EAAB38EA90BD07D358" /> </td> 
   <td colname="col5" align="center" valign="middle"><img href="assets/supported15.png" id="image_D104B9D4E230444B8F76CCE67F91A458" /> </td> 
   <td colname="col7" align="center" valign="middle"><img href="assets/supported15.png" id="image_9BDD011E4C8F48BF981B5D42FD7BE1A9" /> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Playback </td> 
   <td colname="col2"> VOD </td> 
   <td colname="col3"> Trick play </td> 
   <td colname="col4" align="center" valign="middle"><img href="assets/supported15.png" id="image_B0D46404FFDA4F17810E590C49F24114" /> </td> 
   <td colname="col5" align="center" valign="middle"><img href="assets/supported15.png" id="image_E8C7E4C5E1124D23B40ACE4625452AE2" /> </td> 
   <td colname="col7" align="center" valign="middle"><img href="assets/supported15.png" id="image_577B61E8C38B40ED81F38124DF748A78" /> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Playback </td> 
   <td colname="col2"> VOD </td> 
   <td colname="col3"> Smooth trick play </td> 
   <td colname="col4" align="center" valign="middle"><img href="assets/supported15.png" id="image_A4D24A86909C4F63A9D8EFCD507A5FE0" /> </td> 
   <td colname="col5" align="center" valign="middle"><img href="assets/supported15.png" id="image_D59B276150674C75AEAB293E1795BE16" /> </td> 
   <td colname="col7" align="center" valign="middle"> Platform Limitation </td> 
  </tr> 
  <!-- <row> <entry colname="col1">Playback </entry> <entry colname="col2">VOD + Live </entry> <entry colname="col3">Stream integrity </entry> <entry colname="col4" align="center" valign="middle"><image href="images/supported15.png"/> </entry> <entry colname="col5" align="center" valign="middle">Platform Limitation </entry> <entry colname="col7" align="center" valign="middle">Platform Limitation </entry> </row> deprecated 2017 01 26 Eric Wenburg --> 
  <tr> 
   <td colname="col1"> Playback </td> 
   <td colname="col2"> VOD + Live </td> 
   <td colname="col3"> ID3 parsing </td> 
   <td colname="col4" align="center" valign="middle"><img href="assets/supported15.png" id="image_8D0C9782656E4426B0A9C61C39518909" /> </td> 
   <td colname="col5" align="center" valign="middle"><img href="assets/supported15.png" id="image_4607F244EE974227BC3514444E848754" /> </td> 
   <td colname="col7" align="center" valign="middle"> Not Supported </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Playback </td> 
   <td colname="col2"> VOD + Live </td> 
   <td colname="col3"> Discontinuity marker support </td> 
   <td colname="col4" align="center" valign="middle"><img href="assets/supported15.png" id="image_F9A0B66FB11E4B8B91E93980A642916F" /> </td> 
   <td colname="col5" align="center" valign="middle"><img href="assets/supported15.png" id="image_3876661D554D400D841F28F228D326AD" /> </td> 
   <td colname="col7" align="center" valign="middle"><img href="assets/supported15.png" id="image_11F04211B6B747E7BF93D949C96DA97E" /> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Playback </td> 
   <td colname="col2"> VOD + Live </td> 
   <td colname="col3"> Tokenized streams </td> 
   <td colname="col4" align="center" valign="middle"><img href="assets/supported15.png" id="image_130177D668044074854346888AE4B57B" /> </td> 
   <td colname="col5" align="center" valign="middle"><img href="assets/supported15.png" id="image_B69521B6B8B042A88EB1DE0F559F86AF" /> </td> 
   <td colname="col7" align="center" valign="middle"> Platform Limitation </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Playback </td> 
   <td colname="col2"> VOD + Live </td> 
   <td colname="col3"> Billing </td> 
   <td colname="col4" align="center" valign="middle"><img href="assets/supported15.png" id="image_69C41AB12A664692BA51203641B6BCF6" /> </td> 
   <td colname="col5" align="center" valign="middle"><img href="assets/supported15.png" id="image_ED312207D5234475897A8AE592454B64" /> </td> 
   <td colname="col7" align="center" valign="middle"><img href="assets/supported15.png" id="image_75C62EB16797428AA74157631027CE5E" /> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Playback </td> 
   <td colname="col2"> VOD + Live </td> 
   <td colname="col3"> Browserify </td> 
   <td colname="col4" align="center" valign="middle"><img href="assets/supported15.png" id="image_BBBF184B91214AC5B1DD7B06D509CD55" /> </td> 
   <td colname="col5" align="center" valign="middle"><img href="assets/supported15.png" id="image_8B4172B931044F95B9DA45978000E980" /> </td> 
   <td colname="col7" align="center" valign="middle"><img href="assets/supported15.png" id="image_A101F406D0F9404F8296C848ED0D8772" /> </td> 
  </tr> 
 </tbody> 
</table>

#### HLS core playback
<table id="table_0524BD3F2CD1499D95BD4A9D4F451C1B">  
 <thead> 
  <tr> 
   <th colname="col1" morerows="1" class="entry"> Category </th> 
   <th colname="col2" morerows="1" class="entry"> Content type </th> 
   <th colname="col3" morerows="1" class="entry"> Feature </th> 
   <th colname="col4" morerows="1" align="center" class="entry"> Flash </th> 
   <th align="center" class="entry" colspan="2"> HTML5 </th> 
  </tr> 
  <tr> 
   <th colname="col5" align="center" class="entry"> FF, IE, Chrome, Android Chrome </th> 
   <th colname="col7" align="center" class="entry"> Safari, iOS Safari </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Playback </td> 
   <td colname="col2"> VOD + Live </td> 
   <td colname="col3"> General playback (Play, Pause, Seek) </td> 
   <td colname="col4" valign="middle" align="center"><img href="assets/supported15.png" id="image_298A48329E3145DCA55B7C999F57B39B" /> </td> 
   <td colname="col5" valign="middle" align="center"><img href="assets/supported15.png" id="image_C09EE55FBD7142C5B4E33D1F666D3B37" /> </td> 
   <td colname="col7" valign="middle" align="center"><img href="assets/supported15.png" id="image_907B4FBA766D47E5BD6DD2B279C33503" /> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Playback </td> 
   <td colname="col2"> FER VOD </td> 
   <td colname="col3"> General playback (Play, Pause, Seek) </td> 
   <td colname="col4" valign="middle" align="center"><img href="assets/supported15.png" id="image_FBEE44C13A0148829B41C0F761F71B60" /> </td> 
   <td colname="col5" valign="middle" align="center"><img href="assets/supported15.png" id="image_556BCCDE5C5347248EDCC14B9F68D57B" /> </td> 
   <td colname="col7" valign="middle" align="center"><img href="assets/supported15.png" id="image_EA5362AE9B514763896A575775BA30CF" /> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Playback </td> 
   <td colname="col2"> VOD + Live </td> 
   <td colname="col3"> Adaptive bit rate </td> 
   <td colname="col4" valign="middle" align="center"><img href="assets/supported15.png" id="image_220E73AF0B6F4D559877DB62A3F76497" /> </td> 
   <td colname="col5" valign="middle" align="center"><img href="assets/supported15.png" id="image_5BA9E067811243FBB5E9D5628504CBA7" /> </td> 
   <td colname="col7" valign="middle" align="center"><img href="assets/supported15.png" id="image_7F1B0F4743554F54B07A8731651ABE5B" /> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Playback </td> 
   <td colname="col2"> VOD + Live </td> 
   <td colname="col3"> 608/708 captions </td> 
   <td colname="col4" valign="middle" align="center"><img href="assets/supported15.png" id="image_C6F66EB788AF4EE6BAF424B5A8B051D3" /> </td> 
   <td colname="col5" valign="middle" align="center"><img href="assets/supported15.png" id="image_9E3EA8701F4348EB9DBA95407A0D65B6" /> </td> 
   <td colname="col7" valign="middle" align="center"><img href="assets/supported15.png" id="image_B4C92860C9FB43A1B4325F56A441DCEE" /> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Playback </td> 
   <td colname="col2"> VOD + Live </td> 
   <td colname="col3"> WebVTT </td> 
   <td colname="col4" valign="middle" align="center"><img href="assets/supported15.png" id="image_60588206560D487E82EF0055B1486BE4" /> </td> 
   <td colname="col5" valign="middle" align="center"> VOD only </td> 
   <td colname="col7" valign="middle" align="center"> VOD only </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Playback </td> 
   <td colname="col2"> VOD + Live </td> 
   <td colname="col3"> Manifest Failover </td> 
   <td colname="col4" align="center" valign="middle"><img href="assets/supported15.png" id="image_4B1F04ABB9DE4A6B9CE8CDF8E84AE09A" /> </td> 
   <td colname="col5" align="center" valign="middle"><img href="assets/supported15.png" id="image_03F8995C208B453A8057C7732063A585" /> </td> 
   <td colname="col7" align="center" valign="middle"><img href="assets/supported15.png" id="image_574637297FEA4E4AB5991DCABB322F85" /> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Playback </td> 
   <td colname="col2"> VOD + Live </td> 
   <td colname="col3"> Advanced Failover </td> 
   <td colname="col4" align="center" valign="middle"><img href="assets/supported15.png" id="image_24A095376F2B4CA39626F54440BE275B" /> </td> 
   <td colname="col5" align="center" valign="middle"> VOD only </td> 
   <td colname="col7" align="center" valign="middle"> Platform Limitation </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Playback </td> 
   <td colname="col2"> VOD + Live </td> 
   <td colname="col3"> QoS and player notifications </td> 
   <td colname="col4" align="center" valign="middle"><img href="assets/supported15.png" id="image_269FE89B1A594D1C9F9FC55A8D3925E7" /> </td> 
   <td colname="col5" align="center" valign="middle"><img href="assets/supported15.png" id="image_8FC115B67E6D4BDEBAA59F61C6A00D27" /> </td> 
   <td colname="col7" align="center" valign="middle"> Limited QoS support </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Playback </td> 
   <td colname="col2"> VOD + Live </td> 
   <td colname="col3"> Support for cookie headers </td> 
   <td colname="col4" align="center" valign="middle"><img href="assets/supported15.png" id="image_4D8F196D6F7343709DBA5AAE9A3B8F90" /> </td> 
   <td colname="col5" align="center" valign="middle"><img href="assets/supported15.png" id="image_E7D1489F09834D09AB9CDBE35EE437CF" /> </td> 
   <td colname="col7" align="center" valign="middle"> Platform Limitation </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Playback </td> 
   <td colname="col2"> VOD + Live </td> 
   <td colname="col3"> Setting buffer control parameters </td> 
   <td colname="col4" align="center" valign="middle"><img href="assets/supported15.png" id="image_A5D1EA6D2C0C48D48529038FEC261E3E" /> </td> 
   <td colname="col5" align="center" valign="middle"><img href="assets/supported15.png" id="image_03549E9847CB47DDB33A81A029124AFB" /> </td> 
   <td colname="col7" align="center" valign="middle"> Platform Limitation </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Playback </td> 
   <td colname="col2"> VOD + Live </td> 
   <td colname="col3"> Set adaptive bit rate controls </td> 
   <td colname="col4" align="center" valign="middle"><img href="assets/supported15.png" id="image_7504D0DF90EA482390179E669F71D304" /> </td> 
   <td colname="col5" align="center" valign="middle"><img href="assets/supported15.png" id="image_4F4B834E30E24579A5C564EA11E7E928" /> </td> 
   <td colname="col7" align="center" valign="middle"> Platform Limitation </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Playback </td> 
   <td colname="col2"> VOD + Live </td> 
   <td colname="col3"> Custom tags </td> 
   <td colname="col4" align="center" valign="middle"><img href="assets/supported15.png" id="image_EB59B72B81174FFC8D7D88CE34A48B8C" /> </td> 
   <td colname="col5" align="center" valign="middle"><img href="assets/supported15.png" id="image_6325CF663FD84ADE806014D2310CFC07" /> </td> 
   <td colname="col7" align="center" valign="middle"> Platform Limitation </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Playback </td> 
   <td colname="col2"> VOD + Live </td> 
   <td colname="col3"> Late-binding audio </td> 
   <td colname="col4" align="center" valign="middle"><img href="assets/supported15.png" id="image_FE1F72B238E44462BCE3FCF542913599" /> </td> 
   <td colname="col5" align="center" valign="middle"><img href="assets/supported15.png" id="image_2EB13B9C802148F1A4350AADB6C51F14" /> </td> 
   <td colname="col7" align="center" valign="middle"> Platform Limitation </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Playback </td> 
   <td colname="col2"> VOD + Live </td> 
   <td colname="col3"> 302 redirect </td> 
   <td colname="col4" align="center" valign="middle"><img href="assets/supported15.png" id="image_E3C624F5A8524A6CB937A0B3C879B415" /> </td> 
   <td colname="col5" align="center" valign="middle"><img href="assets/supported15.png" id="image_7090F266B7D140D48A1FFCD597099406" /> </td> 
   <td colname="col7" align="center" valign="middle"> Platform Limitation </td> 
  </tr> 
 </tbody> 
</table>


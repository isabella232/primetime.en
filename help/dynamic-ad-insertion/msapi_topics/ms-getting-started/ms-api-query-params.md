---
description: Query parameters tell the manifest server what sort of client sent the request and what that client wants the manifest server to do. Some are required and some have specific acceptable formats or values.
seo-description: Query parameters tell the manifest server what sort of client sent the request and what that client wants the manifest server to do. Some are required and some have specific acceptable formats or values.
seo-title: Manifest server query parameters
title: Manifest server query parameters
uuid: 03632da3-ae20-427c-bd24-4794ab627cc8
index: y
internal: n
snippet: y
---

# Manifest server query parameters{#manifest-server-query-parameters}

Query parameters tell the manifest server what sort of client sent the request and what that client wants the manifest server to do. Some are required and some have specific acceptable formats or values.

The complete URL consists of the base URL followed by a question mark, then `parameterName=value` arguments, separated by ampersands: 
`Base URL?name1=value1&name2=value2& . . .&name n=value n` 

## Recognized parameters {#section_072845B7FA94468C8068E9092983C9E6}

The manifest server recognizes the following parameters. It processes them or passes them, along with all unrecognized parameters, to the ad server. 

<table id="table_98F2BFCED4F54BBCA1690E98CE5DD3DB"> 
 <thead> 
  <tr> 
   <th class="entry"> Key </th> 
   <th class="entry"> Description </th> 
   <th class="entry"> Required </th> 
   <th class="entry"> Valid Values </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td> <span class="codeph"> __sid__ </span> </td> 
   <td> Unique ID that the manifest server uses to generate the session ID. </td> 
   <td> Yes </td> 
   <td> Alphanumeric </td> 
  </tr> 
  <tr> 
   <td> <span class="codeph"> g </span> </td> 
   <td> Client device type </td> 
   <td> When targeting rules depend on device type </td> 
   <td> See list at <a keyref="client_types"></a> (requires Zendesk access) </td> 
  </tr> 
  <tr> 
   <td> <span class="codeph"> k </span> </td> 
   <td> Keywords for custom ad targeting </td> 
   <td> No </td> 
   <td> URL-safe string in format <span class="codeph"> key1=value1;key2=value2;. . . </span> </td> 
  </tr> 
  <tr> 
   <td> <span class="codeph"> u </span> </td> 
   <td> Primetime ad insertion Asset ID. </td> 
   <td> Yes </td> 
   <td> MD5 Hash value </td> 
  </tr> 
  <tr> 
   <td> <span class="codeph"> z </span> </td> 
   <td> Primetime ad insertion Zone ID for the asset. </td> 
   <td> Yes </td> 
   <td> Integer </td> 
  </tr> 
  <tr> 
   <td> <span class="codeph"> enableC3 </span> </td> 
   <td> The client is in a C3 window. If true, replace only local avails; otherwise, replace all avails. </td> 
   <td> No </td> 
   <td> <span class="codeph"> Boolean </span> </td> 
  </tr> 
  <tr> 
   <td colname="c1"> <span class="codeph"> live </span> </td> 
   <td colname="c2"> Indicates whether the content is a Live or VOD (video on-demand) stream. </td> 
   <td colname="c3"> Akamai Ad Scaler or iOS Safari client </td> 
   <td colname="c4"> <span class="codeph"> Boolean </span> </td> 
  </tr> 
  <tr> 
   <td> <span class="codeph"> pabimode </span> </td> 
   <td> <a keyref="partial_ad_break_insertion" format="dita" scope="local"> Enable Partial ad break insertion </a> support <p>Enable if <span class="codeph"> true </span> or <span class="codeph"> start </span> </p> <p>Disable if <span class="codeph"> false </span> </p> </td> 
   <td> No (default is disabled) </td> 
   <td> <span class="codeph"> start </span>, <span class="codeph"> true </span>, or <span class="codeph"> false </span> </td> 
  </tr> 
  <tr> 
   <td> <span class="codeph"> ptadwindow </span> </td> 
   <td> Duration (seconds) of ad stitching window: how far back to look for ads when a DVR user joins the stream. </td> 
   <td> No (default = 1800) </td> 
   <td> 0 to 1800 </td> 
  </tr> 
  <tr> 
   <td> <span class="codeph"> ptassetid </span> </td> 
   <td> Unique ID of the content that is assigned and maintained by publisher. </td> 
   <td> Akamai Ad Scaler </td> 
   <td> URL-safe string </td> 
  </tr> 
  <tr> 
   <td colname="c1"> <span class="codeph"> ptcdn </span> </td> 
   <td colname="c2"> List of one or more CDNs to host transcoded assets. See <a keyref="Multiple_CDN_support_for_CRS_ad_delivery"> Multiple CDN Support </a>. </td> 
   <td colname="c3"> No (default=Akamai) </td> 
   <td colname="c4"> Example: Akamai, Level3, Limelight, Comcast </td> 
  </tr> 
  <tr> 
   <td> <span class="codeph"> ptcueformat </span> </td> 
   <td> The name of the custom ad cue format present in the M3U8. </td> 
   <td> No </td> 
   <td> <span class="codeph"> DPISimple, DPIScte35, Elemental,NBC, NFL, or Turner </span> </td> 
  </tr> 
  <tr> 
   <td> <span class="codeph"> ptfailover </span> </td> 
   <td> Signals the manifest server to identify primary and failover streams specified in the master playlist, and to treat them as disjoint sets. This facilitates failover and prevents timing errors. (For Apple HLS devices only.) See <a keyref="failover_backup_streams"> facilitating HLS player switching </a>. </td> 
   <td> No </td> 
   <td> <span class="codeph"> true </span> </td> 
  </tr> 
  <tr> 
   <td colname="c1"> <span class="codeph"> ptmulticall </span> </td> 
   <td colname="c2"> If set to <span class="codeph"> true </span>, multiple Auditude ad-calls for FER made; one for each ad-break. <p> If absent or set to <span class="codeph"> false </span>, one ad-call is made to auditude for FER. </p> </td> 
   <td colname="c3"> No </td> 
   <td colname="c4"> <span class="codeph"> Boolean </span> <p> <p>Note:  The following requirements: 
      <ul id="ul_083B79079C9B43E2B2979B0980A6B9DE"> 
       <li id="li_654C41D516A94E60A12304E6C93DE6A5"> <span class="codeph"> ptcueformat </span> parameter must be set to <span class="codeph"> nbc </span> </li> 
       <li id="li_DA47F80AD5214DEDBD1224986AA8F3AF"> <span class="codeph"> pttimeline </span> parameter is ignored. </li> 
      </ul> </p> </p> </td> 
  </tr> 
  <tr> 
   <td> <span class="codeph"> ptplayer </span> </td> 
   <td> Player making the request. </td> 
   <td> iOS/Safari </td> 
   <td> <span class="codeph"> ios-mobileweb </span> </td> 
  </tr> 
  <tr> 
   <td> <span class="codeph"> ptrendition </span> </td> 
   <td> Auto-generated by ad insertion and used by Akamai. Do not add or remove. </td> 
   <td> Akamai Ad Scaler </td> 
   <td> </td> 
  </tr> 
  <tr> 
   <td> <span class="codeph"> pttagds </span> </td> 
   <td> Enable #EXT-X- DISCONTINUITY- SEQUENCE tags (see <a keyref="ext-x-ds_spec"></a>) </td> 
   <td> No </td> 
   <td> <span class="codeph"> true </span> - manifest server includes a sequence tag before the content in each m3u8 file it sends; if parameter is not present or not <span class="codeph"> true </span>, manifest server does not include a sequence tag. </td> 
  </tr> 
  <tr> 
   <td> <span class="codeph"> pttimeline </span> </td> 
   <td> A string containing the desired timeline for ad placement and content, which overrides ad breaks in the content stream. </td> 
   <td> No </td> 
   <td> VOD timeline (see <a keyref="vod_time_fmt"></a>) </td> 
  </tr> 
  <tr> 
   <td> <span class="codeph"> pttoken </span> </td> 
   <td> Enable TS segment authorization tokens <p> <p>Note:  Only Akamai CDN tokens supported </p> </p> </td> 
   <td> For TS segment authorization tokens </td> 
   <td> <span class="codeph"> Boolean </span> </td> 
  </tr> 
  <tr> 
   <td> <span class="codeph"> pttrackingmode </span> </td> 
   <td> Enable ad tracking; either custom client-side (simple), server-side (sstm), or hybrid (simplesstm). </td> 
   <td> No </td> 
   <td> <span class="codeph"> simple </span>, <span class="codeph"> sstm </span>, or <span class="codeph"> simplesstm </span> <p>Note:  If this parameter is not included, the #EX-X-MARKER is injected into the manifest. See <a keyref="about_ext-x-marker"></a>. </p> </td> 
  </tr> 
  <tr> 
   <td> <span class="codeph"> pttrackingposition </span> </td> 
   <td> Instructs the manifest server to return ad tracking information only. Do not specify this parameter in the <span class="codeph"> bootstrap </span> request. </td> 
   <td> Client-side Tracking </td> 
   <td> Alphanumeric <p> <p>Note:  The manifest server ignores all passed values. However, if you pass a <span class="codeph"> null </span> or empty string, the manifest server returns the M3U8 instead of tracking information. </p> </p> </td> 
  </tr> 
  <tr> 
   <td> <span class="codeph"> pttrackingversion </span> </td> 
   <td> The format version of the client-side tracking information. </td> 
   <td> Client-side Tracking </td> 
   <td> <span class="codeph"> v1 </span>, <span class="codeph"> v2 </span>, <span class="codeph"> v3 </span>, or <span class="codeph"> vmap </span> </td> 
  </tr> 
  <tr> 
   <td colname="c1"> <span class="codeph"> scteTracking </span> </td> 
   <td colname="c2"> <p> Fetch <span class="codeph"> M3U8 </span>, before <span class="codeph"> SCTE </span> tracking information can be fetched in JSON V2 sidecar. </p> <p>This parameter indicates to the manifest server that the player fetching the <span class="codeph"> M3U8 </span> needs <span class="codeph"> SCTE </span> tag information to be retrieved. </p> </td> 
   <td colname="c3"> No (default: <span class="codeph"> false </span>) </td> 
   <td colname="c4"> <span class="codeph"> true </span> or <span class="codeph"> false </span> <p>Note:  The SCTE-35 data is returned in the JSON sidecar with the following combination of query parameter values: 
     <ul id="ul_D1CAA2A9C2FC42C69736E62EA2BA98AF"> 
      <li id="li_0DDE536C25A64D918FFF7F0149308FBC">ptcueformat=turner | elemental | nfl | DPIScte35 </li> 
      <li id="li_0B581826714A4D7DB58980D8BF284EAF">pttrackingversion=v2 </li> 
      <li id="li_8E4D4F836DB74A5BBF7584777A43F43B">scteTracking=true </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="c1"> <span class="codeph"> vetargetmultiplier </span> </td> 
   <td colname="c2"> The number of segments from the live point <p>The pre-roll offset is configured using: </p> <p> ( <span class="codeph"> vetargetmultiplier </span> * <span class="codeph"> targetduration </span>) + <span class="codeph"> vebufferlength </span> </p> <p>Note:  Live/Linear only </p> </td> 
   <td colname="c3"> No (default: <span class="codeph"> 3.0 </span>) </td> 
   <td colname="c4"> <span class="codeph"> Float </span> </td> 
  </tr> 
  <tr> 
   <td colname="c1"> <span class="codeph"> vebufferLength </span> </td> 
   <td colname="c2"> <p>The number of seconds from the live point </p> <p>Note:  Live/Linear only </p> </td> 
   <td colname="c3"> No (default: <span class="codeph"> 3.0 </span>) </td> 
   <td colname="c4"> <span class="codeph"> Float </span> </td> 
  </tr> 
 </tbody> 
</table>


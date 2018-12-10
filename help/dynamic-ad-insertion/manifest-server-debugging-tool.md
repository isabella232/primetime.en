---
title: Manifest Server Debugging Tool
seo-title: Manifest Server Debugging Tool
description: null
seo-description: Manifest Server Debugging Tool
uuid: 0b4f06f5-4b1f-4f88-980a-5b4df28e0094
acrolinxstatus: not_checked
contentOwner: asgupta
cq-lastmodifiedby: vishgupt
products: SG_PRIMETIME
topic-tags: ad-insertion
discoiquuid: 00b49659-ce56-4b5c-87cd-c357a0936641
donotlocalize: false
moreHelpPaths: /content/help/en/primetime/morehelp/ad-insertion;/content/help/en/primetime/morehelp/ad-insertion
pagecreatedat: en
pagelayout: video
sidecolumn: left
index: y
internal: n
snippet: y
---

# Manifest Server Debugging Tool{#manifest-server-debugging-tool}

## Overview of debugging tool {#overview-of-debugging-tool}

The debugging tool enables publishers to investigate potentially costly ad insertion problems by examining debugging information returned in real time by the manifest server in HTTP headers or, when more detailed information is needed, examining session logs after the fact. Adobe partners like Akamai can use the tool to debug their integrations with Primetime ad decisioning.

The tool supports debugging ad insertion problems in any of the main manifest server ad tracking configurations:

* Client-side tracking with a player based on TVSDK.
* Client-side tracking with a player not based on TVSDK.
* Server-side tracking.

To support all of these cases, the tool does not require or use player publisher codes.

When you initiate a manifest server session, you can set a parameter on the request URL to ask it to log debugging information. Using different values of that parameter, you can also ask the manifest server to return specified pieces of debugging information in HTTP headers, but headers can contain only a limited amount of information. You can obtain credentials from Adobe to access complete log files, which the manifest server saves periodically (for example, hourly) on an archive server. Once you have credentials for that server, you can access it directly at any time.

## Debugging tool options {#debugging-tool-options}

When invoking the debugging tool, you have several options for what information the manifest server returns in HTTP headers. The options do not affect what the manifest server places in log files.

### Specifying ptdebug {#specifying-ptdebug}

When initiating debug logging for a manifest server session, you can add the ptdebug parameter to the request URL to specify the following options for the information that the manifest server returns in HTTP headers:

* ptdebug=true All records except TRACE_HTTP_HEADER and most call/response data from TRACE_AD_CALL records.
* ptdebug=AdCall Only TRACE_AD_*type *(for example, TRACE_AD_CALL) records.
* ptdebug=Header Only TRACE_HTTP_HEADER records.

The options do not affect what the manifest server places in the log files. You have no control of that, but the log files are text files, so you can apply a wide variety of tools to extract and reformat the information that interests you.

Here is an example of the HTTP header returned when ptdebug=Header. Some long strings of hex digits are replaced by ". . ." for clarity.

```
X-ADBE-AI-DBG-1 TRACE_MISC    HTTP request received
X-ADBE-AI-DBG-2 TRACE_MISC    Processing Variant
X-ADBE-AI-DBG-3 TRACE_MISC    Valid URL received.
X-ADBE-AI-DBG-4 TRACE_MISC    Initialize new session
X-ADBE-AI-DBG-5 TRACE_MISC    Requesting: /auditude/variant/pubAsset/aHR0cDovL . . .m3u8
 ?u=cecebae . . .&z=189962&pttrackingmode=simple&pttrackingversion=v1
 &ptcueformat=turner&__sid__=yk-sat953pm-112
 &ptdebug=true
X-ADBE-AI-DBG-6  TRACE_HTTP_HEADER  MAIN  REQUEST  Host    bWFuaWZl. . .
X-ADBE-AI-DBG-7  TRACE_HTTP_HEADER  MAIN  REQUEST  Connection       Y2xvc2U=
X-ADBE-AI-DBG-8  TRACE_HTTP_HEADER  MAIN  REQUEST  Accept   dGV4dC. . .
X-ADBE-AI-DBG-9  TRACE_HTTP_HEADER  MAIN  REQUEST  Cookie   c3NhaT. . .
X-ADBE-AI-DBG-10 TRACE_HTTP_HEADER  MAIN  REQUEST  User-Agent       TW96aWxs. . .
X-ADBE-AI-DBG-11 TRACE_HTTP_HEADER  MAIN  REQUEST  Accept-Language  ZW4tdXM=
X-ADBE-AI-DBG-12 TRACE_HTTP_HEADER  MAIN  REQUEST  Accept-Encoding  Z3ppcCwg. . .=
X-ADBE-AI-DBG-13 TRACE_REQUEST_INFO  200   GET
 /auditude/variant/pubAsset/aHR0cD. . ..m3u8
 ?u=cecebae72a919de350b9ac52602623f3&z=189962&pttrackingmode=simple
 &pttrackingversion=v1&ptcueformat=turner&__sid__=yk-sat953pm-112
 &ptdebug=true   0 0 0   Variant  NA  null  null  127.0.0.1:43357
X-ADBE-AI-DBG-14 TRACE_HTTP_HEADER  MAIN  RESPONSE Content-Type     YXBwbG. . .
X-ADBE-AI-DBG-15 TRACE_HTTP_HEADER  MAIN  RESPONSE Cache-Control    bm8tY2. . .
X-ADBE-AI-DBG-16 TRACE_HTTP_HEADER  MAIN  RESPONSE Access-Control-Allow-Origin    Kg==
X-ADBE-AI-DBG-17 TRACE_MISC   Done
```

## Formats of log records {#formats-of-log-records}

Each log record has a type and a set of fields, some of which might be optional. The fields of all records up to the record type are the same. They provide a timestamp and information about the session. The record type identifies the kind of event being logged, and subsequent fields provide information about the logged event.

The structure of a log record is as follows:

`datetime request_id session_id zone_id record_type` *other fields.*

<table border="1" cellpadding="1" cellspacing="0" width="100%"> 
 <tbody> 
  <tr> 
   <td valign="top" width="191"><p><strong>Field</strong></p> </td> 
   <td valign="top" width="150"><p><strong>Type</strong></p> </td> 
   <td valign="top" width="331"><p><strong>Description</strong></p> </td> 
  </tr> 
  <tr> 
   <td valign="top" width="191"><p>datetime</p> </td> 
   <td valign="top" width="150"><p>string</p> </td> 
   <td valign="top" width="331"><p>Timestamp</p> </td> 
  </tr> 
  <tr> 
   <td valign="top" width="191"><p>request_id</p> </td> 
   <td valign="top" width="150"><p>string</p> </td> 
   <td valign="top" width="331"><p>Request ID used by the manifest server (unix timestamp)</p> </td> 
  </tr> 
  <tr> 
   <td valign="top" width="191"><p>session_id</p> </td> 
   <td valign="top" width="150"><p>string</p> </td> 
   <td valign="top" width="331"><p>Session ID used by the manifest server</p> </td> 
  </tr> 
  <tr> 
   <td valign="top" width="191"><p>zone_id</p> </td> 
   <td valign="top" width="150"><p>integer</p> </td> 
   <td valign="top" width="331"><p>Zone ID</p> </td> 
  </tr> 
  <tr> 
   <td valign="top" width="191"><p>record_type</p> </td> 
   <td valign="top" width="150"><p>string</p> </td> 
   <td valign="top" width="331"><p>Type of event being logged</p> </td> 
  </tr> 
  <tr> 
   <td valign="top" width="191"><p><em>other fields</em></p> </td> 
   <td valign="top" width="150"><p>***</p> </td> 
   <td valign="top" width="331"><p>Depend on type of event</p> </td> 
  </tr> 
 </tbody> 
</table>

### TRACE_REQUEST_INFO records {#trace-request-info-records}

Records of this type log the results of HTTP requests. Fields beyond TRACE_REQUEST_INFO appear in the order shown in the table, separated by tabs.

<table border="1" cellpadding="1" cellspacing="0" width="100%"> 
 <tbody> 
  <tr> 
   <td valign="top" width="231"><p><strong>Field</strong></p> </td> 
   <td valign="top" width="152"><p><strong>Type</strong></p> </td> 
   <td valign="top" width="289"><p><strong>Description</strong></p> </td> 
  </tr> 
  <tr> 
   <td valign="top" width="231"><p>status</p> </td> 
   <td valign="top" width="152"><p>string</p> </td> 
   <td valign="top" width="289"><p>Returned HTTP status code</p> </td> 
  </tr> 
  <tr> 
   <td valign="top" width="231"><p>request_method</p> </td> 
   <td valign="top" width="152"><p>string</p> </td> 
   <td valign="top" width="289"><p>HTTP method (GET or POST)</p> </td> 
  </tr> 
  <tr> 
   <td valign="top" width="231"><p>request_uri</p> </td> 
   <td valign="top" width="152"><p>string</p> </td> 
   <td valign="top" width="289"><p>HTTP request URI (without host)</p> </td> 
  </tr> 
  <tr> 
   <td valign="top" width="231"><p>request_length</p> </td> 
   <td valign="top" width="152"><p>integer</p> </td> 
   <td valign="top" width="289"><p>Length of request (bytes)</p> </td> 
  </tr> 
  <tr> 
   <td valign="top" width="231"><p>response_length</p> </td> 
   <td valign="top" width="152"><p>integer</p> </td> 
   <td valign="top" width="289"><p>Length of response (bytes)</p> </td> 
  </tr> 
  <tr> 
   <td valign="top" width="231"><p>delta</p> </td> 
   <td valign="top" width="152"><p>integer</p> </td> 
   <td valign="top" width="289"><p>Time (milliseconds) to process request</p> </td> 
  </tr> 
  <tr> 
   <td valign="top" width="231"><p>module_type</p> </td> 
   <td valign="top" width="152"><p>string</p> </td> 
   <td valign="top" width="289"><p>Variant, Stream, or VOD</p> </td> 
  </tr> 
  <tr> 
   <td valign="top" width="231"><p>remote_address_aud_client_ip</p> </td> 
   <td valign="top" width="152"><p>string</p> </td> 
   <td valign="top" width="289"><p>(see note)</p> </td> 
  </tr> 
  <tr> 
   <td valign="top" width="231"><p>remote_address_x_fwd_for_hdr_key</p> </td> 
   <td valign="top" width="152"><p>string</p> </td> 
   <td valign="top" width="289"><p>(see note)</p> </td> 
  </tr> 
  <tr> 
   <td valign="top" width="231"><p>remote_host_port</p> </td> 
   <td valign="top" width="152"><p>string</p> </td> 
   <td valign="top" width="289"><p>(see note)</p> </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>The last three fields are optional.

An example:

```
1427263800524 6495aafc-3f34-4047-ad36-350d4f056eb4 189938
TRACE_REQUEST_INFO 301 GET /auditude/variant/pubAsset/aHR0cDov. . ..m3u8
?u=cecebae72a919de350b9ac52602623f3&z=189938&ptcueformat=turner& sid =yk-cnnlive-003 &ptdebug=true 0 0 0 Variant 111.22.3.44 111.22.3.45 127.0.0.1:46383

```

### TRACE_HTTP_HEADER records {#trace-http-header-records}

Records of this type log HTTP headers exchanged during HTTP calls between the manifest server and client, ad server, or content server. Fields beyond TRACE_HTTP_HEADER appear in the order shown in the table, separated by tabs.

<table border="1" cellpadding="1" cellspacing="0" width="100%"> 
 <tbody> 
  <tr> 
   <td valign="top" width="201"><p><strong>Field</strong></p> </td> 
   <td valign="top" width="145"><p><strong>Type</strong></p> </td> 
   <td valign="top" width="326"><p><strong>Description</strong></p> </td> 
  </tr> 
  <tr> 
   <td valign="top" width="201"><p>request_type</p> </td> 
   <td valign="top" width="145"><p>string</p> </td> 
   <td valign="top" width="326"><p>Type of request (MAIN or UNKNOWN)</p> </td> 
  </tr> 
  <tr> 
   <td valign="top" width="201"><p>request_response</p> </td> 
   <td valign="top" width="145"><p>string</p> </td> 
   <td valign="top" width="326"><p>Response header (request or response)</p> </td> 
  </tr> 
  <tr> 
   <td valign="top" width="201"><p>header_name</p> </td> 
   <td valign="top" width="145"><p>string</p> </td> 
   <td valign="top" width="326"><p>HTTP header name</p> </td> 
  </tr> 
  <tr> 
   <td valign="top" width="201"><p>header_value</p> </td> 
   <td valign="top" width="145"><p>string</p> </td> 
   <td valign="top" width="326"><p>Base64-encoded HTTP header value</p> </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>The request_type and header_value fields are optional.

An example:

```
2015-03-25T06:10:00.927Z  1427263800573  6495aa. . .  189938 TRACE_MISC
    Requesting: /cnn/tvecnn/stream4/stream_Layer.m3u8
2015-03-25T06:10:00.927Z  1427263800573  6495aa. . .  189938 TRACE_HTTP_HEADER
    UNKNOWN REQUEST Cookie  aGRu. . .
2015-03-25T06:10:00.928Z  1427263800573  6495aa. . .  189938 TRACE_HTTP_HEADER
    UNKNOWN REQUEST User-Agent  TW96aW. . .
2015-03-25T06:10:01.063Z  1427263800573  6495aa. . .  189938 TRACE_HTTP_HEADER
    UNKNOWN RESPONSE  Server  bmd4X2. . .
2015-03-25T06:10:01.063Z  1427263800573  6495aa. . .  189938 TRACE_HTTP_HEADER
    UNKNOWN RESPONSE  Content-Type    YXBwb. . .
2015-03-25T06:10:01.063Z  1427263800573  6495aa. . .  189938 TRACE_HTTP_HEADER
    UNKNOWN RESPONSE  Last-Modified   V2VkL. . .
2015-03-25T06:10:01.063Z  1427263800573  6495aa. . .  189938 TRACE_HTTP_HEADER
    UNKNOWN RESPONSE  ETag    IjIyY2. . .
2015-03-25T06:10:01.063Z  1427263800573  6495aa. . .  189938 TRACE_HTTP_HEADER
    UNKNOWN RESPONSE  Vary    QWNjZXB. . .
2015-03-25T06:10:01.063Z  1427263800573  6495aa. . .  189938 TRACE_HTTP_HEADER
    UNKNOWN RESPONSE  Cache-Control   bWF4LW. . .
2015-03-25T06:10:01.064Z  1427263800573  6495aa. . .  189938 TRACE_HTTP_HEADER
    UNKNOWN RESPONSE  Expires V2VkL. . .
2015-03-25T06:10:01.064Z  1427263800573  6495aa. . .  189938 TRACE_HTTP_HEADER
    UNKNOWN RESPONSE  Date    V2VkLCA. . .
2015-03-25T06:10:01.064Z  1427263800573  6495aa. . .  189938 TRACE_HTTP_HEADER
    UNKNOWN RESPONSE  Age MQ==
2015-03-25T06:10:01.064Z  1427263800573  6495aa. . .  189938 TRACE_HTTP_HEADER
    UNKNOWN RESPONSE  Via MS4xIH. . .
```

### TRACE_AD_CALL records {#trace-ad-call-records}

Records of this type log the results of manifest server ad requests. Fields beyond TRACE_AD_CALL appear in the order shown in the table, separated by tabs.

<table border="1" cellpadding="1" cellspacing="0" width="100%"> 
 <tbody> 
  <tr> 
   <td valign="top" width="177"><p><strong>Field</strong></p> </td> 
   <td valign="top" width="127"><p><strong>Type</strong></p> </td> 
   <td valign="top" width="367"><p><strong>Description</strong></p> </td> 
  </tr> 
  <tr> 
   <td valign="top" width="177"><p>status</p> </td> 
   <td valign="top" width="127"><p>string</p> </td> 
   <td valign="top" width="367"><p>Returned HTTP status code</p> </td> 
  </tr> 
  <tr> 
   <td valign="top" width="177"><p>request_duration</p> </td> 
   <td valign="top" width="127"><p>integer</p> </td> 
   <td valign="top" width="367"><p>Time (milliseconds) from request to response</p> </td> 
  </tr> 
  <tr> 
   <td valign="top" width="177"><p>ad_server_query_url</p> </td> 
   <td valign="top" width="127"><p>string</p> </td> 
   <td valign="top" width="367"><p>URL for the ad call, including query parameters</p> </td> 
  </tr> 
  <tr> 
   <td valign="top" width="177"><p>ad_system_id</p> </td> 
   <td valign="top" width="127"><p>string</p> </td> 
   <td valign="top" width="367"><p>Ad system, from the ad server response (Auditude if not specified)</p> </td> 
  </tr> 
  <tr> 
   <td valign="top" width="177"><p>avail_id</p> </td> 
   <td valign="top" width="127"><p>string</p> </td> 
   <td valign="top" width="367"><p>ID of the avail, from the ad cue in the content manifest file (N/A for VOD)</p> </td> 
  </tr> 
  <tr> 
   <td valign="top" width="177"><p>avail_duration</p> </td> 
   <td valign="top" width="127"><p>number</p> </td> 
   <td valign="top" width="367"><p>Duration (seconds) of the avail, from the ad cue in the content manifest file (N/A for VOD)</p> </td> 
  </tr> 
  <tr> 
   <td valign="top" width="177"><p>ad_server_response</p> </td> 
   <td valign="top" width="127"><p>string</p> </td> 
   <td valign="top" width="367"><p>Base64-encoded response from ad server</p> </td> 
  </tr> 
 </tbody> 
</table>

An example:

```
2015-03-25T06:13:31.271Z 14272. . . 189938 TRACE_AD_CALL
200 8 http://ad.stg2.auditude.com/adserver/a?cip=0.0.0.0&g=1000012&of=1.5 &ptcueformat=turner&ptdebug=true&tl=l,150,30,m&tm=63&u=ceceb. . . Auditude IvpIyC. . . 150 PD94bWw. . .

```

### TRACE_AD_INSERT, TRACE_AD_RESOLVE, and TRACE_AD_REDIRECT records {#trace-ad-insert-trace-ad-resolve-and-trace-ad-redirect-records}

Records of this type log the results of the ad requests indicated by the record type. Fields beyond the record type appear in the order shown in the table, separated by tabs.

<table border="1" cellpadding="1" cellspacing="0" width="100%"> 
 <tbody> 
  <tr> 
   <td valign="top" width="163"><p><strong>Field</strong></p> </td> 
   <td valign="top" width="132"><p><strong>Type</strong></p> </td> 
   <td valign="top" width="377"><p><strong>Description</strong></p> </td> 
  </tr> 
  <tr> 
   <td valign="top" width="163"><p>status</p> </td> 
   <td valign="top" width="132"><p>string</p> </td> 
   <td valign="top" width="377"><p>Returned HTTP status code</p> </td> 
  </tr> 
  <tr> 
   <td valign="top" width="163"><p>avail_id</p> </td> 
   <td valign="top" width="132"><p>string</p> </td> 
   <td valign="top" width="377"><p>ID of the avail, from the ad cue in the content manifest file (live) or from the manifest server (VOD)</p> </td> 
  </tr> 
  <tr> 
   <td valign="top" width="163"><p>ad_type</p> </td> 
   <td valign="top" width="132"><p>string</p> </td> 
   <td valign="top" width="377"><p>Type of ad (DIRECT or REDIRECT)</p> </td> 
  </tr> 
  <tr> 
   <td valign="top" width="163"><p>ad_duration</p> </td> 
   <td valign="top" width="132"><p>integer</p> </td> 
   <td valign="top" width="377"><p>Duration (seconds) of ad, from ad server response</p> </td> 
  </tr> 
  <tr> 
   <td valign="top" width="163"><p>ad_content_url</p> </td> 
   <td valign="top" width="132"><p>string</p> </td> 
   <td valign="top" width="377"><p>URL of the ad's manifest file, from the ad server response</p> </td> 
  </tr> 
  <tr> 
   <td valign="top" width="163"><p>ad_content_url_actual</p> </td> 
   <td valign="top" width="132"><p>string</p> </td> 
   <td valign="top" width="377"><p>URL of the inserted ad's manifest file. Empty for</p> <p>TRACE_AD_REDIRECT.</p> </td> 
  </tr> 
  <tr> 
   <td valign="top" width="163"><p>ad_system_id</p> </td> 
   <td valign="top" width="132"><p>string</p> </td> 
   <td valign="top" width="377"><p>Ad system, from the ad server response (Auditude if not specified)</p> </td> 
  </tr> 
  <tr> 
   <td valign="top" width="163"><p>ad_id</p> </td> 
   <td valign="top" width="132"><p>string</p> </td> 
   <td valign="top" width="377"><p>ID of the ad, from the ad server response</p> </td> 
  </tr> 
  <tr> 
   <td valign="top" width="163"><p>creative_id</p> </td> 
   <td valign="top" width="132"><p>string</p> </td> 
   <td valign="top" width="377"><p>ID of the creative, from the ad node, from the ad server response</p> </td> 
  </tr> 
  <tr> 
   <td valign="top" width="163"><p>ad_call_id</p> </td> 
   <td valign="top" width="132"><p>string</p> </td> 
   <td valign="top" width="377"><p>Not used. Reserved for future use.</p> </td> 
  </tr> 
  <tr> 
   <td valign="top" width="163"><p>delta</p> </td> 
   <td valign="top" width="132"><p>integer</p> </td> 
   <td valign="top" width="377"><p>Time (milliseconds) taken by this event</p> </td> 
  </tr> 
  <tr> 
   <td valign="top" width="163"><p>misc</p> </td> 
   <td valign="top" width="132"><p>string</p> </td> 
   <td valign="top" width="377"><p>Reason ad was skipped</p> </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>The ad_content_url_actual, ad_call_id, and misc fields are optional.

For TRACE_AD_RESOLVE and TRACE_AD_INSERT, the URL in the ad_content_url_actual field is for the transcoded ad if one is available. Otherwise the field is empty for TRACE_AD_RESOLVE or the same as ad_content_url for TRACE_AD_INSERT.

An example:

```
2015-03-18T22:25:36.229-07:00 1426742736208 1120feb. . . 147465 TRACE_AD_RESOLVE
200 0 DIRECT 15 http://cdn2.auditude.com/assets/3p/v2/8c/2b/8c2bb. . ..m3u8 Auditude 308008 0  cecebae72a919de350b9ac52602623f3 0 NA

2015-03-18T22:25:36.230-07:00 1426742736208 1120feb. . . 147465 TRACE_AD_RESOLVE
200 2 DIRECT 15 http://cdn2.auditude.com/assets/3p/v2/8c/2b/8c2bb. . ..m3u8 Auditude 308008 0  cecebae72a919de350b9ac52602623f3 0 NA

2015-03-18T22:25:36.562-07:00 1426742736208 1120feb. . . 147465 TRACE_AD_INSERT
200 0 DIRECT 15 http://cdn2.auditude.com/assets/3p/v2/8c/2b/8c2bb. . ..m3u8 http://cdn2.auditude.com/assets/3p/v2/8c/2b/8c2bb. . ..m3u8
Auditude 308008 0 cecebae72a919de350b9ac52602623f3 0 NA
2015-03-18T22:25:36.563-07:00 1426742736208 1120feb. . . 147465 TRACE_AD_INSERT
200 2 DIRECT 15 http://cdn2.auditude.com/assets/3p/v2/8c/2b/8c2bb. . ..m3u8 http://cdn2.auditude.com/assets/3p/v2/8c/2b/8c2bb. . ..m3u8
Auditude 308008 0 cecebae72a919de350b9ac52602623f3 0 NA

```

### TRACE_TRACKING_URL records {#trace-tracking-url-records}

Records of this type log the results of manifest server ad requests. Fields beyond TRACE_TRACKING_URL appear in the order shown in the table, separated by tabs.

<table border="1" cellpadding="1" cellspacing="0" width="100%"> 
 <tbody> 
  <tr> 
   <td valign="top" width="148"><p><strong>Field</strong></p> </td> 
   <td valign="top" width="164"><p><strong>Type</strong></p> </td> 
   <td valign="top" width="360"><p><strong>Description</strong></p> </td> 
  </tr> 
  <tr> 
   <td valign="top" width="148"><p>pts</p> </td> 
   <td valign="top" width="164"><p>number</p> </td> 
   <td valign="top" width="360"><p>Program timestamp. Time within video to call the URL.</p> </td> 
  </tr> 
  <tr> 
   <td valign="top" width="148"><p>ad_system</p> </td> 
   <td valign="top" width="164"><p>string</p> </td> 
   <td valign="top" width="360"><p>Ad system (auditude or freewheel)</p> </td> 
  </tr> 
  <tr> 
   <td valign="top" width="148"><p>url</p> </td> 
   <td valign="top" width="164"><p>string</p> </td> 
   <td valign="top" width="360"><p>URL pinged</p> </td> 
  </tr> 
  <tr> 
   <td valign="top" width="148"><p>status</p> </td> 
   <td valign="top" width="164"><p>string</p> </td> 
   <td valign="top" width="360"><p>HTTP status returned from the ping</p> </td> 
  </tr> 
 </tbody> 
</table>

An example:

```
2015-06-04T23:24:42.000-0700    1426742736208     3086f5cd . . .    12345    TRACE_TRACKING_URL
    0.000000    ExampleSystem    http://localhost/index.php?stream:test#8.1433485415;
    sid:3086f5cd . . .;pts:0    200
```

### TRACE_TRANSCODING_NO_MEDIA_TO_TRANSCODE records {#trace-transcoding-no-media-to-transcode-records}

Records of this type log a missing ad creative. The only field beyond TRACE_TRANSCODING_NO_MEDIA_TO_TRANSCODE appears in the table.

<table border="1" cellpadding="1" cellspacing="0" width="100%"> 
 <tbody> 
  <tr> 
   <td valign="top" width="114"><p><strong>Field</strong></p> </td> 
   <td valign="top" width="119"><p><strong>Type</strong></p> </td> 
   <td valign="top" width="439"><p><strong>Description</strong></p> </td> 
  </tr> 
  <tr> 
   <td valign="top" width="114"><p>ad_id</p> </td> 
   <td valign="top" width="119"><p>string</p> </td> 
   <td valign="top" width="439"><p>Fully qualified ad ID (FQ_AD_ID: Q_AD_ID[;Q_AD_ID[;Q_AD_ID...]] Q_AD_ID: PROTOCOL:AD_SYSTEM:AD_ID[:CREATIVE_ID[:MEDIA_ID]] PROTOCOL: AUDITUDE,VAST)</p> </td> 
  </tr> 
 </tbody> 
</table>

### TRACE_TRANSCODING_REQUESTED records {#trace-transcoding-requested-records}

Records of this type log the results of transcoding requests that the manifest server sends to CRS. Fields beyond TRACE_TRANSCODING_REQUESTED appear in the order shown in the table, separated by tabs.

<table border="1" cellpadding="1" cellspacing="0" width="100%"> 
 <tbody> 
  <tr> 
   <td valign="top" width="174"><p><strong>Field</strong></p> </td> 
   <td valign="top" width="137"><p><strong>Type</strong></p> </td> 
   <td valign="top" width="361"><p><strong>Description</strong></p> </td> 
  </tr> 
  <tr> 
   <td valign="top" width="174"><p>ad_id</p> </td> 
   <td valign="top" width="137"><p>string</p> </td> 
   <td valign="top" width="361"><p>Fully qualified ad ID</p> </td> 
  </tr> 
  <tr> 
   <td valign="top" width="174"><p>ad_manifest_url</p> </td> 
   <td valign="top" width="137"><p>string</p> </td> 
   <td valign="top" width="361"><p>URL of the ad's manifest file, from the ad server response</p> </td> 
  </tr> 
  <tr> 
   <td valign="top" width="174"><p>creative_type</p> </td> 
   <td valign="top" width="137"><p>string</p> </td> 
   <td valign="top" width="361"><p>Type of media</p> </td> 
  </tr> 
  <tr> 
   <td valign="top" width="174"><p>flags</p> </td> 
   <td valign="top" width="137"><p>string</p> </td> 
   <td valign="top" width="361"><p>ID3 indicates whether the transcoding request includes a request to add an ID3 tag</p> </td> 
  </tr> 
  <tr> 
   <td valign="top" width="174"><p>target_duration</p> </td> 
   <td valign="top" width="137"><p>string</p> </td> 
   <td valign="top" width="361"><p>Target duration (seconds) of the transcoded creative</p> </td> 
  </tr> 
 </tbody> 
</table>

### TRACE_TRACKING_REQUEST records {#trace-tracking-request-records}

Records of this type indicate a request to do server side tracking. Fields beyond TRACE_TRACKING_REQUEST appear in the order shown in the table, separated by tabs.

<table border="1" cellpadding="1" cellspacing="0" width="100%"> 
 <tbody> 
  <tr> 
   <td valign="top" width="162"><p><strong>Field</strong></p> </td> 
   <td valign="top" width="135"><p><strong>Type</strong></p> </td> 
   <td valign="top" width="375"><p><strong>Description</strong></p> </td> 
  </tr> 
  <tr> 
   <td valign="top" width="162"><p>tracking_url_count</p> </td> 
   <td valign="top" width="135"><p>integer</p> </td> 
   <td valign="top" width="375"><p>Number of tracking URLs</p> </td> 
  </tr> 
  <tr> 
   <td valign="top" width="162"><p>start</p> </td> 
   <td valign="top" width="135"><p>float</p> </td> 
   <td valign="top" width="375"><p>PTS fragment start time (seconds with millisecond precision)</p> </td> 
  </tr> 
  <tr> 
   <td valign="top" width="162"><p>end</p> </td> 
   <td valign="top" width="135"><p>float</p> </td> 
   <td valign="top" width="375"><p>PTS fragment end time (seconds with millisecond precision)</p> </td> 
  </tr> 
 </tbody> 
</table>

### TRACE_TRACKING_REQUEST_URL records {#trace-tracking-request-url-records}

Records of this type provide a tracking URL for server side tracking. Fields beyond TRACE_TRACKING_REQUEST_URL appear in the order shown in the table, separated by tabs.

<table border="1" cellpadding="1" cellspacing="0" width="100%"> 
 <tbody> 
  <tr> 
   <td valign="top" width="155"><p><strong>Field</strong></p> </td> 
   <td valign="top" width="141"><p><strong>Type</strong></p> </td> 
   <td valign="top" width="376"><p><strong>Description</strong></p> </td> 
  </tr> 
  <tr> 
   <td valign="top" width="155"><p>timestamp</p> </td> 
   <td valign="top" width="141"><p>float</p> </td> 
   <td valign="top" width="376"><p>Time (seconds, with precision .001) within the playback session to ping the tracking URL</p> </td> 
  </tr> 
  <tr> 
   <td valign="top" width="155"><p>ad_system</p> </td> 
   <td valign="top" width="141"><p>string</p> </td> 
   <td valign="top" width="376"><p>Ad system (for example, auditude)</p> </td> 
  </tr> 
  <tr> 
   <td valign="top" width="155"><p>url</p> </td> 
   <td valign="top" width="141"><p>string</p> </td> 
   <td valign="top" width="376"><p>URL to ping</p> </td> 
  </tr> 
 </tbody> 
</table>

### TRACE_WEBVTT_REQUEST records {#trace-webvtt-request-records}

Records of this type log requests the manifest server makes for WEBVTT captions. Fields beyond TRACE_WEBVTT_REQUEST appear in the order shown in the table, separated by tabs.

<table border="1" cellpadding="1" cellspacing="0" width="100%"> 
 <tbody> 
  <tr> 
   <td valign="top" width="149"><p><strong>Field</strong></p> </td> 
   <td valign="top" width="149"><p><strong>Type</strong></p> </td> 
   <td valign="top" width="375"><p><strong>Description</strong></p> </td> 
  </tr> 
  <tr> 
   <td valign="top" width="149"><p>status</p> </td> 
   <td valign="top" width="149"><p>string</p> </td> 
   <td valign="top" width="375"><p>Returned HTTP status code</p> </td> 
  </tr> 
  <tr> 
   <td valign="top" width="149"><p>vtt_uri</p> </td> 
   <td valign="top" width="149"><p>string</p> </td> 
   <td valign="top" width="375"><p>URL for request</p> </td> 
  </tr> 
  <tr> 
   <td valign="top" width="149"><p>start</p> </td> 
   <td valign="top" width="149"><p>float</p> </td> 
   <td valign="top" width="375"><p>Split start time (seconds with millisecond precision)</p> </td> 
  </tr> 
  <tr> 
   <td valign="top" width="149"><p>end</p> </td> 
   <td valign="top" width="149"><p>float</p> </td> 
   <td valign="top" width="375"><p>Split end time (seconds with millisecond precision)</p> </td> 
  </tr> 
 </tbody> 
</table>

### TRACE_WEBVTT_RESPONSE records {#trace-webvtt-response-records}

Records ``of ``this ``type ``log ``responses ``the ``manifest ``server ``sends ``to ``clients ``in `` `answer` ``to ``requests `` `for` ``WEBVTT ``captions. Fields beyond TRACE_WEBVTT_RESPONSE ``appear in the order shown in the table, separated `by`tabs.

<table border="1" cellpadding="1" cellspacing="0" width="100%"> 
 <tbody> 
  <tr> 
   <td valign="top" width="166"><p><strong>Field</strong></p> </td> 
   <td valign="top" width="158"><p><strong>Type</strong></p> </td> 
   <td valign="top" width="348"><p><strong>Description</strong></p> </td> 
  </tr> 
  <tr> 
   <td valign="top" width="166"><p>status</p> </td> 
   <td valign="top" width="158"><p>string</p> </td> 
   <td valign="top" width="348"><p>Returned HTTP status code</p> </td> 
  </tr> 
  <tr> 
   <td valign="top" width="166"><p>response</p> </td> 
   <td valign="top" width="158"><p>string</p> </td> 
   <td valign="top" width="348"><p>Base64-encoded response sent to client</p> </td> 
  </tr> 
 </tbody> 
</table>

### TRACE_WEBVTT_SOURCE records {#trace-webvtt-source-records}

Records of this type log responses to requests the manifest server makes for WEBVTT captions. Fields beyond TRACE_WEBVTT_SOURCE appear in the order shown in the table, separated by tabs.

<table border="1" cellpadding="1" cellspacing="0" width="100%"> 
 <tbody> 
  <tr> 
   <td valign="top" width="161"><p><strong>Field</strong></p> </td> 
   <td valign="top" width="161"><p><strong>Type</strong></p> </td> 
   <td valign="top" width="351"><p><strong>Description</strong></p> </td> 
  </tr> 
  <tr> 
   <td valign="top" width="161"><p>status</p> </td> 
   <td valign="top" width="161"><p>string</p> </td> 
   <td valign="top" width="351"><p>Returned HTTP status code</p> </td> 
  </tr> 
  <tr> 
   <td valign="top" width="161"><p>source</p> </td> 
   <td valign="top" width="161"><p>string</p> </td> 
   <td valign="top" width="351"><p>Base64-encoded original VTT content</p> </td> 
  </tr> 
 </tbody> 
</table>

### TRACE_MISC records {#trace-misc-records}

Records of this type enable the manifest server to log events and information not otherwise planned for when it ingests ads. The field beyond TRACE_MISC consists of a message string. Messages that might appear include the following:

• Ad ignored :AdPlacement [adManifestURL=http://cdn2.auditude.com/assets/3p/v2/8c/2b/8c2bb. . . .m3u8, durationSeconds=15.0, ignore=false, redirectAd=false, priority=1]

• AdPlacement adManifestURL=*adManifestURL*, durationSeconds=*seconds*, ignore=*ignore*, redirectAd=*redirectAd*, priority=*priority*

• Ad placement returned null.

• Ad successfully stitched.

• Ad call failed : *error message*.

• Adding User-Agent to fetch raw manifest: *user-agent*.

• Adding cookie to fetch raw manifest: [cookie]

• Bad URL *requested URL error message*. (Failed to parse variant URL)

• Called url: *URL *got return: *response code*. ( Live URL)

• Called url: *URL *return code: *response code*. ( VOD URL)

• Conflict found while resolving ads: either one of - mid-roll start or mid-roll end falls within pre-roll or pre-roll contained in mid-roll (VOD).

• Detected unhandled exception thrown by the handler for URI: *request URL*.

• Done generating variant manifest. (Variant)

• Done generating variant manifest.

• Exception in handling VAST redirect *redirect URL *error: *error message*.

• Failed to fetch ad's playlist for *ad manifest URL*.

• Failed to generate targeted manifest. (HLSManifestResolver)

• Failed to parse first ad call response: *error message*.

• Failed to process *GET|POST *request for path: *request URL*. (Live/VOD)

• Failed to process live manifest request: *request URL*. (Live)

• Failed to return a variant manifest: *error message*.

• Failed to validate group ID: *group ID*.

• Fetching raw manifest: *content URL*. (Live)

• Following VAST redirect: *redirect URL*.

• Found empty avails. (VOD)

• Found *number *ads. (VOD)

• HTTP request received. (Very first message)

• Ignoring ad because difference between ad response duration (*ad response duration *sec) and actual ad duration (*actual duration *sec) is larger than the limit. (HLSManifestResolver)

• Ignoring avail that provided no ID value. (GroupAdResolver.java)

• Ignoring avail that provided invalid time value: *time *for availId = *avail ID*.

• Ignoring avail that provided invalid duration value: *duration *for availId = *avail ID*.

• Initialize new session. (Variant)

• Invalid HTTP method. It must be a GET. (VOD)

• Invalid HTTP method. Tracking request must be a GET. (Live)

• Invalid URL *requested URL error message*. (Variant)

• Invalid group. (HLSManifestResolver)

• Invalid request. Caption is not a valid tracking request. (VOD)

• Invalid request. Caption request must be made after session is established. (VOD)

• Invalid request. Tracking request must be made after session is established. (VOD)

• Invalid server instance for overload group ID: *group ID*. (Live)

• Limit of VAST redirects reached - *number*.

• Making ad call: *ad call URL*.

• No manifest found for: *content URL*. (Live)

• No matching avail found for avail ID: *avail ID*. (HLSManifestResolver)

• No playback session found. (HLSManifestResolver)

• Processing VOD request for manifest *content URL*.

• Processing variant.

• Processing caption request for manifest *content URL*.

• Processing tracking request. (VOD)

• Redirect ad response empty. ( VASTStAX)

• Requesting: *URL*.

• Returning error response for GET request because no playback session was found. (VOD)

• Returning error response for GET request because of an internal server error.

• Returning error response for GET request specifying an invalid asset: *ad request ID*. (VOD)

• Returning error response for GET request specifying an invalid or empty group ID: *group ID*. (VOD)

• Returning error response for GET request specifying an invalid tracking position value. (VOD)

• Returning error response for GET request with invalid syntax - *request URL*. (Live/VOD)

• Returning error response for request with unsupported HTTP method: *GET|POST*. (Live/VOD)

• Returning manifest from cache. (VOD)

• Server is overloaded. Proceed without ad stitch request. (Variant)

• Start generating targeted manifest. (HLSManifestResolver)

• Start generating variant manifest from: *content URL*. (Variant)

• Start stitching ads into manifest. (VODHLSResolver)

• Trying to stitch ad at *HH:MM:SS*: AdPlacement [adManifestURL=*ad Manifest URL*, durationSeconds=*seconds*, ignore=*ignore*, redirectAd=*redirect ad*, priority=*priority*. (HLSManifestResolver)

• Unable to get ads because of invalid pttimeline - returned the content without ads. (VOD)

• Unable to get ads - returned the content without ads. (VOD)

• Unable to get ad query and no content URL was given. (VOD)

• Valid URL received. (VOD/Variant)

• Variant M3U8 not found. (Variant)

### TRACE_TRACKING_URL records {#trace-tracking-url-records-1}

The manifest server generates records of this kind after calling a tracking URL during the server side tracking workflow. Fields beyond TRACE_TRACKING_URL appear in the order shown in the table, separated by tabs.

<table border="1" cellpadding="1" cellspacing="0" width="100%"> 
 <tbody> 
  <tr> 
   <td valign="top" width="159"><p><strong>Field</strong></p> </td> 
   <td valign="top" width="178"><p><strong>Type</strong></p> </td> 
   <td valign="top" width="335"><p><strong>Description</strong></p> </td> 
  </tr> 
  <tr> 
   <td valign="top" width="159"><p>pts</p> </td> 
   <td valign="top" width="178"><p>number</p> </td> 
   <td valign="top" width="335"><p>PTS time within stream</p> </td> 
  </tr> 
  <tr> 
   <td valign="top" width="159"><p>ad_system</p> </td> 
   <td valign="top" width="178"><p>string</p> </td> 
   <td valign="top" width="335"><p>Ad's ad system (auditude or freewheel)</p> </td> 
  </tr> 
  <tr> 
   <td valign="top" width="159"><p>url</p> </td> 
   <td valign="top" width="178"><p>string</p> </td> 
   <td valign="top" width="335"><p>URL pinged</p> </td> 
  </tr> 
  <tr> 
   <td valign="top" width="159"><p>state</p> </td> 
   <td valign="top" width="178"><p>string</p> </td> 
   <td valign="top" width="335"><p>HTTP status code</p> </td> 
  </tr> 
 </tbody> 
</table>

### TRACE_PLAYBACK_PROGRESS records {#trace-playback-progress-records}

The manifest server generates records of this kind when it receives a signal about playback progress during the server side tracking workflow. Fields beyond TRACE_PLAYBACK_PROGRESS appear in the order shown in the table, separated by tabs.

<table border="1" cellpadding="1" cellspacing="0" width="100%"> 
 <tbody> 
  <tr> 
   <td valign="top" width="195"><p><strong>Field</strong></p> </td> 
   <td valign="top" width="158"><p><strong>Type</strong></p> </td> 
   <td valign="top" width="319"><p><strong>Description</strong></p> </td> 
  </tr> 
  <tr> 
   <td valign="top" width="195"><p>status</p> </td> 
   <td valign="top" width="158"><p>string</p> </td> 
   <td valign="top" width="319"><p>HTTP status code</p> </td> 
  </tr> 
  <tr> 
   <td valign="top" width="195"><p>bandwidth</p> </td> 
   <td valign="top" width="158"><p>integer</p> </td> 
   <td valign="top" width="319"><p>Bandwidth of the stream</p> </td> 
  </tr> 
  <tr> 
   <td valign="top" width="195"><p>pts</p> </td> 
   <td valign="top" width="158"><p>integer</p> </td> 
   <td valign="top" width="319"><p>PTS time within stream</p> </td> 
  </tr> 
  <tr> 
   <td valign="top" width="195"><p>ms_time</p> </td> 
   <td valign="top" width="158"><p>integer</p> </td> 
   <td valign="top" width="319"><p>Time when manifest server generated tracking URL</p> </td> 
  </tr> 
  <tr> 
   <td valign="top" width="195"><p>url</p> </td> 
   <td valign="top" width="158"><p>string</p> </td> 
   <td valign="top" width="319"><p>Redirect URL</p> </td> 
  </tr> 
  <tr> 
   <td valign="top" width="195"><p>header_user_agent</p> </td> 
   <td valign="top" width="158"><p>string</p> </td> 
   <td valign="top" width="319"><p>HTTP User-Agent header</p> </td> 
  </tr> 
  <tr> 
   <td valign="top" width="195"><p>header_dnt</p> </td> 
   <td valign="top" width="158"><p>integer</p> </td> 
   <td valign="top" width="319"><p>HTTP do-not-track header</p> </td> 
  </tr> 
  <tr> 
   <td valign="top" width="195"><p>effective_remote_address</p> </td> 
   <td valign="top" width="158"><p>string</p> </td> 
   <td valign="top" width="319"><p>IPv4 effective remote address</p> </td> 
  </tr> 
  <tr> 
   <td valign="top" width="195"><p>remote_address</p> </td> 
   <td valign="top" width="158"><p>string</p> </td> 
   <td valign="top" width="319"><p>IPv4 remote address</p> </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>The last four fields are optional.


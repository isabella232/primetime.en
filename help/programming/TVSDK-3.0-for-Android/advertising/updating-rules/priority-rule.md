---
description: The priority rule defines the priority order of the ad creatives that will be selected for playback from a VAST/VMAP response.
seo-description: The priority rule defines the priority order of the ad creatives that will be selected for playback from a VAST/VMAP response.
seo-title: Priority rules
title: Priority rules
uuid: 08dbd2e3-1210-4210-9791-dc531f80cfbc
index: y
internal: n
snippet: y
---

# Priority rules{#priority-rules}

The priority rule defines the priority order of the ad creatives that will be selected for playback from a VAST/VMAP response.

#### A Priority rule has the following attributes and possible values:
<table id="table_ljp_tgx_hz">  
 <thead> 
  <tr> 
   <th class="entry"> Key </th> 
   <th class="entry"> Type </th> 
   <th class="entry"> Values </th> 
   <th class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td><span class="codeph"> priority</span> </td> 
   <td><span class="codeph"> Array</span> </td> 
   <td></td> 
   <td> An array of lowercase mime-types that define the priority in which source creatives must be selected for playback. </td> 
  </tr> 
  <tr> 
   <td><span class="codeph"> item</span> </td> 
   <td><span class="codeph"> String</span> </td> 
   <td><span class="codeph"> host</span> </td> 
   <td>Currently only <span class="codeph"> host</span> is supported. This attribute must be present when <span class="codeph"> matches</span> and <span class="codeph"> values</span> attributes are defined. </td> 
  </tr> 
  <tr> 
   <td><span class="codeph"> matches</span> </td> 
   <td><span class="codeph"> String</span> </td> 
   <td><span class="codeph"> multiple</span> </td> 
   <td>Possible values: 
    <ul id="ul_tnf_2hx_hz"> 
     <li id="li_4B8568F50A594F6183BED8B5562BE556"><span class="codeph"> eq</span> - equals </li> 
     <li id="li_2EC118C8A8C1460793685C12D69426D6"><span class="codeph"> ne</span> - not equals </li> 
     <li id="li_827770C65C564C58A5B5BE963490BB0C"><span class="codeph"> co</span> - contains </li> 
     <li id="li_637109AA23AB4FEE8A1B7A9767628052"><span class="codeph"> nc</span> - not contains </li> 
     <li id="li_F56FEF0A663049D38C79C5D6578A100D"><span class="codeph"> sw</span> - starts with </li> 
     <li id="li_A4A7FB9314204717AF6BB23A48D3E9C1"><span class="codeph"> ew</span> - ends with </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td><span class="codeph"> type</span> </td> 
   <td><span class="codeph"> String</span> </td> 
   <td><span class="codeph"> priority</span> </td> 
   <td>The value must always be <span class="codeph"> priority</span> </td> 
  </tr> 
  <tr> 
   <td><span class="codeph"> values</span> </td> 
   <td><span class="codeph"> Array</span> </td> 
   <td></td> 
   <td> <p>TVSDK will use the <span class="codeph"> matches</span> attribute on the <span class="codeph"> item</span> of the source creative and match against the values defined in this array </p> </td> 
  </tr> 
  <tr> 
   <td><span class="codeph"> stream</span> </td> 
   <td><span class="codeph"> String</span> </td> 
   <td></td> 
   <td> <p>Value can be <span class="codeph"> vod</span> or <span class="codeph"> live</span> </p> </td> 
  </tr> 
 </tbody> 
</table>

<a id="example_D0630AEDD4EF4AC9BEFF931B9B2B0AF2"></a>

```
{
    "ads": {
        "rules": {
            "default": [
                {
                    "
<b>type</b>": "
<b>priority</b>",
                    "
<b>stream</b>": "vod",
                    "
<b>priority</b>": [
                        "application/x-mpegurl",
                        "application/vnd.apple.mpegurl",
                        "application/x-shockwave-flash",
                        "video/mp4",
                        "video/m4v",
                        "video/x-flv",
                        "video/webm"
                    ]
                },
                {
                    ...
                },
            ]
        }
    }
}

```


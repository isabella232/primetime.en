---
description: The normalize rule defines a URL transformation to apply to a source creative URL obtained from a VAST/VMAP response.
seo-description: The normalize rule defines a URL transformation to apply to a source creative URL obtained from a VAST/VMAP response.
seo-title: Normalize rules
title: Normalize rules
uuid: 1de18a89-0256-4a93-b35b-e81784928a96
index: y
internal: n
snippet: y
---

# Normalize rules{#normalize-rules}

The normalize rule defines a URL transformation to apply to a source creative URL obtained from a VAST/VMAP response.

#### The normalize rule has the following attributes and possible values:
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
   <td><span class="codeph"> type</span> </td> 
   <td><span class="codeph"> String</span> </td> 
   <td><span class="codeph"> normalize</span> </td> 
   <td>The value must always be <span class="codeph"> normalize</span>. </td> 
  </tr> 
  <tr> 
   <td><span class="codeph"> item</span> </td> 
   <td><span class="codeph"> String</span> </td> 
   <td><span class="codeph"> host</span> </td> 
   <td>Currently only <span class="codeph"> host</span> is supported. This attribute must be present when <span class="codeph"> matches</span> and <span class="codeph"> values</span> attributes are defined. </td> 
  </tr> 
  <tr> 
   <td><span class="codeph"> matches</span> </td> 
   <td></td> 
   <td></td> 
   <td>Possible values: 
    <ul id="ul_tnf_2hx_hz"> 
     <li id="li_41368CC08DCE442E985CF09B877E5876"><span class="codeph"> eq</span> - equals </li> 
     <li id="li_1D5D3B03109F4A7D9C13BAAB5E24087B"><span class="codeph"> ne</span> - not equals </li> 
     <li id="li_DE6335DC1F4A4852A0C3EA42E4B08727"><span class="codeph"> co</span> - contains </li> 
     <li id="li_FF3DD247ECA54B62AEF7A06A06DD2C27"><span class="codeph"> nc</span> - not contains </li> 
     <li id="li_0583FF0D10D843429A63C8D7D10C4E08"><span class="codeph"> sw</span> - starts with </li> 
     <li id="li_D0EC0F5EE7C14354B01C5F0EFDDF635D"><span class="codeph"> ew</span> - ends with </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td><span class="codeph"> values</span> </td> 
   <td><span class="codeph"> Array</span> </td> 
   <td></td> 
   <td>TVSDK will use the <span class="codeph"> matches</span> attribute on the <span class="codeph"> item</span> of the source creative and match against the values defined in this array. </td> 
  </tr> 
  <tr> 
   <td><span class="codeph"> find</span> </td> 
   <td><span class="codeph"> regex</span> </td> 
   <td></td> 
   <td> A regular expression to apply on the source creative URL to match. </td> 
  </tr> 
  <tr> 
   <td><span class="codeph"> replace</span> </td> 
   <td><span class="codeph"> regex</span> </td> 
   <td></td> 
   <td> A regular expression to apply on the source creative URL to replace based on the match. </td> 
  </tr> 
 </tbody> 
</table>

<a id="example_C750A00F6F514CE0BD96815D59E53537"></a>

```
{
    "ads": {
        "rules": {
            "default": [
                {
                ...
                }
                {
                    "
<b>type</b>": "
<b>normalize</b>",
                    "
<b>item</b>": "host",
                    "
<b>matches</b>": "ew",
                    "
<b>values</b>": [
                        "redirector.gvt1.com"
                    ],
                    "
<b>find</b>": "videoplayback/(.*?)/expire/.*?/(.*?)/signature/.*?/",
                    "
<b>replace</b>": "videoplayback/$1/expire//$2/signature//"
                }                
            ]
        }
    }
}
```


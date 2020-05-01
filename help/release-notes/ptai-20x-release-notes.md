---
title:  PTAI 20.5.1 release notes
description: PTAI 20.5.1 release notes describe what is new or changed, the resolved and known issues in Primetime Dynamic Ad Insertion in the year 2020.
---

# Primetime Dynamic Ad Insertion 20.5.1 Release Notes

Dynamic Ad Insertion 20.3.3 release notes describe what is new or changed, issues resolved and known issues in Primetime Dynamic Ad Insertion in the year 2020.

## What's new in PTAI 20.5.1

**When:** Tuesday, May 5, 2020 from 04:00 AM to 05:00 AM EASTERN

* Fixed an issue to ensure the correct CORS headers are provided when If-Modified-Since headers are sent.

* Bug fixes on the CRS dashboard

* Maintenance updates.

## What changed in previous releases

### Version 20.3.4

**When:** Wednesday, April 1, 2020 from 03:00 AM to 04:00 AM EASTERN

* Fixed an issue that caused subtitles to go out of sync after ad insertion in VOD/WebVTT.

* Security updates.

### Version 20.3.3

**When:** Thursday, March 26, 2020 from 03:00am to 04:00am EASTERN

* SSAI 4XX and 5XX responses now correctly supply CORS-related headers, allowing cross-domain javascript/webview clients to successfully read error responses.

* Fixed an issue with X-Forwarded-For headers, where IPv6 addresses were not correctly URL encoded when passed to the ad servers.

* Fixed an issue with CMAF/demuxed audio streams, where in certain scenarios EXT-X-MEDIA-SEQUENCE numbers would increment incorrectly

### Version 20.1.3

**When:** Tuesday, January 28, 2020 from 2:00am to 03:00am EASTERN

* **VMAP with FER support for "nbc" CueFormat**

Convert cues from FER stream into FW timeline override params, when ptcueformat=nbc is used and the stream is a VOD stream with in-manifest cues and baked-in ads.

* Sanitize user-agent field in HTTP Header before forwarding to 3rd party Ad providers/CDN.

* Filter out control/non-printable characters (ascii code < 32) from "user-agent" HTTP headers before sending to Auditude and other ad-providers,CDNs. Auditude Ad-Call used to fail for such invalid headers.

* Purge old V1 Objects from NetStorage Groups to keep object count within safe limits of Akamai.

## Resolved issues

Where resolution is associated with a reported issue, a Zendesk reference is displayed. For example ZD#xxxxx.

**PTAI 20.3.3**

* Issue with X-Forwarded-For headers, where IPv6 addresses were not correctly URL encoded when passed to the ad servers.

* Issue with CMAF/demuxed audio streams, where in certain scenarios EXT-X-MEDIA-SEQUENCE numbers increment incorrectly in certain scenarios

## Known issues and limitations

**PTAI 20.3.3**

No new limitation added.

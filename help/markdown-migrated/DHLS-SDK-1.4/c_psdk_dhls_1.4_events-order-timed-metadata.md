---
description: dispatches timed metadata events and generates timed metadata whenever default or custom tags are encountered or when a playlist changes in a manifest. Events are dispatched in the order in which they appear in the manifest.
seo-description: dispatches timed metadata events and generates timed metadata whenever default or custom tags are encountered or when a playlist changes in a manifest. Events are dispatched in the order in which they appear in the manifest.
seo-title: Timed metadata events
title: Timed metadata events
---

# Timed metadata events

Your player implements actions based on the following events:
* `codeph TimedMetadataEvent.TIMED_METADATA_ID3_ADDED`: Dispatched when an ID3 timed metadata was processed.
* `codeph TimedMetadataEvent.TIMED_METADATA_SKIPPED`: Dispatched when timed metadata was processed and no opportunity was detected.


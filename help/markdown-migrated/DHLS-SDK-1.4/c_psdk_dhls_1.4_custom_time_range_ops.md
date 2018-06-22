---
description: Ad deletion and replacement are implemented with custom markers that identify different types of time ranges in a VOD stream: mark, delete, and replace. For each custom time range, you can perform associated operations, including deleting or replacing ad content.
seo-description: Ad deletion and replacement are implemented with custom markers that identify different types of time ranges in a VOD stream: mark, delete, and replace. For each custom time range, you can perform associated operations, including deleting or replacing ad content.
seo-title: Custom time range operations
title: Custom time range operations
---

# Custom time range operations

For ad deletion and replacement,  includes the following *custom time range operation* modes:
* MARK - Dispatches `codeph AdBreak` events for the marked regions. (This was called `codeph customAdMarker` in previous versions of .) Ad insertion is not allowed in this mode.
* DELETE - For this mode, the app uses the `codeph TimeRangeCollection` class to define time regions for C3 Ad Deletion. Ad insertion is allowed in this mode.
* REPLACE - In this mode, the app replaces a `codeph timeRange` with an  `codeph AdBreak`. The replace operation starts where the C3 Ad deletion occurs, and ends at the indicated time (shorter or longer than the original time range).

provides a `codeph CustomRangesOpportunityGenerator` class to generate placement opportunities for the MARK and DELETE ranges. For the REPLACE mode,  generates two placement opportunities for each time range:
* The `codeph CustomRangeResolver` generates placement opportunities for DELETE
* The `codeph AuditudeAdResolver` generates placement opportunities for INSERT


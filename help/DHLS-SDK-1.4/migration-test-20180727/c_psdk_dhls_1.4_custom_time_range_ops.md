---
description: Ad deletion and replacement are implemented with custom markers that identify different types of time ranges in a VOD stream: mark, delete, and replace. For each custom time range, you can perform associated operations, including deleting or replacing ad content.
seo-description: Ad deletion and replacement are implemented with custom markers that identify different types of time ranges in a VOD stream: mark, delete, and replace. For each custom time range, you can perform associated operations, including deleting or replacing ad content.
seo-title: Custom time range operations
title: Custom time range operations
uuid: 3060a617-5d51-4e5f-a3e0-ed15bacd28b4
index: n
internal: n
snippet: y
translate: y
---

# Custom time range operations

For ad deletion and replacement,  <!-- PH element: phrases/primetime-sdk-name --> includes the following*custom time range operation* modes: 
* MARK - Dispatches `AdBreak` events for the marked regions. (This was called `customAdMarker` in previous versions of  <!-- PH element: phrases/primetime-sdk-name --> .) Ad insertion is not allowed in this mode.
* DELETE - For this mode, the app uses the `TimeRangeCollection` class to define time regions for C3 Ad Deletion. Ad insertion is allowed in this mode.
* REPLACE - In this mode, the app replaces a `timeRange` with an  <!-- PH element: phrases/auditude-name-long --> `AdBreak`. The replace operation starts where the C3 Ad deletion occurs, and ends at the indicated time (shorter or longer than the original time range).

<!-- PH element: phrases/primetime-sdk-name --> provides a `CustomRangesOpportunityGenerator` class to generate placement opportunities for the MARK and DELETE ranges. For the REPLACE mode,  <!-- PH element: phrases/primetime-sdk-name --> generates two placement opportunities for each time range:
* The `CustomRangeResolver` generates placement opportunities for DELETE
* The `AuditudeAdResolver` generates placement opportunities for INSERT


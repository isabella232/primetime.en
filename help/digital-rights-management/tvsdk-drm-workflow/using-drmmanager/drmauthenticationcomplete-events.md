---
seo-title: Handling DRMAuthenticationComplete Events
title: Handling DRMAuthenticationComplete Events
uuid: ed40300a-4287-4512-a78b-04159c122877
---

# Handling DRMAuthenticationComplete Events{#handling-drmauthenticationcomplete-events}

The `DRMManager` dispatches a `DRMAuthenticationCompleteEvent` object when a user is successfully authenticated through a call to the `authenticate()` method. The `DRMAuthenticationCompleteEvent` object contains a reusable token that can be used to persist user authentication across application sessions. Pass this token to `DRMManager` `setAuthenticationToken()` method to re-establish the session. (The token creator sets token attributes such as expiration. Adobe does not provide an API for examining token attributes.) 

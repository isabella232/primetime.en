---
seo-title: Handling DRMAuthenticationComplete Events
title: Handling DRMAuthenticationComplete Events
uuid: 41356313-7ed8-427b-b0b0-26e4a438b047
index: y
internal: n
snippet: y
---

# Handling DRMAuthenticationComplete Events{#handling-drmauthenticationcomplete-events}

The `DRMManager` dispatches a `DRMAuthenticationCompleteEvent` object when a user is successfully authenticated through a call to the `authenticate()` method. The `DRMAuthenticationCompleteEvent` object contains a reusable token that can be used to persist user authentication across application sessions. Pass this token to `DRMManager` `setAuthenticationToken()` method to re-establish the session. (The token creator sets token attributes such as expiration. Adobe does not provide an API for examining token attributes.) 

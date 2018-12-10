---
description: You can generate Expressplay tokens for their encrypted content by sending token requests to the appropriate Expressplay token server.
seo-description: You can generate Expressplay tokens for their encrypted content by sending token requests to the appropriate Expressplay token server.
seo-title: Expressplay tokens
title: Expressplay tokens
uuid: c9fd5d7c-af57-4142-8e38-8f2a24ff3c46
index: y
internal: n
snippet: y
---

# Expressplay tokens{#expressplay-tokens}

You can generate Expressplay tokens for their encrypted content by sending token requests to the appropriate Expressplay token server.

An example is the following URL: 
The content encryption key storage ID or CEKSID given to the `kid` parameter and the content encryption key or CEK given to the `contentKey` parameter must match the content encryption key storage ID and content encryption key used for packaging. The following text is an example of the token server response: 
You can then either

* use the returned URL and query as the license server URL, or 
* take out the query from the URL and pass in the ExpressPlayToken separately as a HTTP POST header


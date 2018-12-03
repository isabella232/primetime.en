---
description: You can use TVSDK to send arbitrary data in cookie headers for session management, gate access, and so on.
seo-description: You can use TVSDK to send arbitrary data in cookie headers for session management, gate access, and so on.
seo-title: Work with cookies
title: Work with cookies
uuid: f49a0ff8-f9ca-4b29-9b16-b13b3f9c1fc9
index: y
internal: n
snippet: y
---

# Work with cookies{#work-with-cookies}

You can use TVSDK to send arbitrary data in cookie headers for session management, gate access, and so on.

Here is a sample request to the key server with some authentication:

1. Your customer logs in to your website in a browser and their login shows that this customer is allowed to view content. 
1. Based on what is expected by the license server, your application generates an authentication token.

   This value is passed to TVSDK. 
1. TVSDK sets this value in the cookie header. 
1. When TVSDK makes a request to the key server to get a key to decrypt the content, the request contains the authentication value in the cookie header.

   The key server knows that the request is valid.

To work with cookies: 

1. Create a `cookieManager` and add your cookies for the URIs to your cookieStore.

   For example: 

   ```java
   CookieManager cookieManager=new CookieManager(); 
   CookieHandler.setDefault(cookieManager);  
   HttpCookie cookie=new HttpCookie("lang","fr"); 
   cookie.setDomain("twitter.com");  
   cookie.setPath("/"); 
   cookie.setVersion(0); 
   cookieManager.getCookieStore().add(newURI("http://twitter.com/"),cookie);
   ```

   >[!TIP]
   >
   >When 302 redirect is enabled, the ad request may be redirected to a domain that is different from the domain to which the cookie belongs.

   TVSDK queries this `cookieManager` at runtime, checks whether there are any cookies associated with the URL, and automatically uses those cookies. 

The event MediaPlayerEvent.COOKIES_UPDATED is called when C++ cookies are updated. This cookiesUpdatedEvent has a method getCookieString() that returns a string value for the cookie.

A sample code snippet is below: 

```
private final CookiesUpdatedEventListener cookiesUpdatedEventListener = new CookiesUpdatedEventListener()  
{ 
@Override 
public void onCookiesUpdated(CookiesUpdatedEvent cookiesUpdatedEvent) 
 { 
 String cookieStr = cookiesUpdatedEvent.getCookieString();  
 logger.i(LOG_TAG + "::MediaPlayer.CookiesUpdatedEventListener#onCookiesUpdated()", "cookieStr " + cookieStr);  
 }  
};
```

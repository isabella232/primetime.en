---
description: You can use notifications to implement real-time logging in your video application.
seo-description: You can use notifications to implement real-time logging in your video application.
seo-title: Add real-time logging and debugging
title: Add real-time logging and debugging
---

# Add real-time logging and debugging

The notification system allows you to gather logging and debugging information for diagnostics and validation without stressing the system.

>[!IMPORTANT]
>
>The logging back end is not part of a production setup and is not expected to handle high-load traffic. If your implementation does not need to be absolutely complete, consider the efficiency of data transmission to avoid overloading your system.
Here is an example of how to retrieve notifications:

>1. Create a timer-based execution thread for your video application that periodically queries the data gathered by the  notification system.
>   
>1. If the timer's interval is too large, and the size of the event list is too small, the notification event list will overflow.
>   To avoid this overflow, do one of the following:
>    * Decrease the time interval that drives the thread that polls for new events.
>    * Increase the size of the notification list.
>   
>1. Serialize the latest notification event entries in JSON format and send the entries to a remote server for postprocessing.
>   The remote server can graphically display the provided data in real-time.
>   
>1. To detect the loss of notification events, look for gaps in the sequence of event index values.
>   <!-- Regarding this next statement? I don't think so... -->
 <!-- Each notification event has an index value that is automatically incremented by the 
<span class="codeph">session.NotificationHistory</span> class. -->
>   
>   

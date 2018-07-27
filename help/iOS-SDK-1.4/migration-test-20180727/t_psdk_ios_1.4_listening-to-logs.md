---
seo-title: Listening to logs
title: Listening to logs
uuid: 1f34d655-d2ea-4da0-a78f-4de28ad71b68
index: n
internal: n
snippet: y
translate: y
---

# Listening to logs

To register for listening to logs:
>1. Implement a custom class that follows the protocol ` PTLogger`:
>
>   ```
>   @implementation PTConsoleLogger 
>    
>   + (PTConsoleLogger *) consoleLogger { 
>       return [[[PTConsoleLogger alloc] init] autorelease]; 
>   } 
>    
>   - (void)logEntry:(PTLogEntry *)entry { 
>       //Log the message to the console using NSLog  
>       NSLog(@"[%@] %@", entry.tag, entry.message); 
>   } 
>    
>   @end
>   ```
>
>1. To register the instance to receive logging entries, add an instance of the ` PTLogger` to the ` PTLoggerFactory`:
>
>   ```
>   PTConsoleLogger *logger = [PTConsoleLogger consoleLogger]; 
>   // Either use the addLogger method: 
>   [[PTLogFactory sharedInstance] addLogger:(logger)] 
>    
>   //Or replace the preceding line with this macro for ease of use 
>   //PTLogAddLogger(logger); 
>   
>   ```
>

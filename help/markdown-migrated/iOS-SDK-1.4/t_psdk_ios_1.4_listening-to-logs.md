---
seo-title: Listening to logs
title: Listening to logs
---

# Listening to logs

To register for listening to logs:
>1. Implement a custom class that follows the protocol `codeph  PTLogger`:
>   ```
>   @implementation PTConsoleLogger 
>    
>   + (PTConsoleLogger *) consoleLogger { 
>    return [[[PTConsoleLogger alloc] init] autorelease]; 
>   } 
>    
>   - (void)logEntry:(PTLogEntry *)entry { 
>    //Log the message to the console using NSLog 
>    NSLog(@"[%@] %@", entry.tag, entry.message); 
>   } 
>    
>   @end
>   ```
>   
>   
>1. To register the instance to receive logging entries, add an instance of the `codeph  PTLogger` to the `codeph  PTLoggerFactory`:
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
>   
>   

---
seo-title: Listen to logs
title: Listen to logs
uuid: 226f645f-aa4c-4a5f-8509-4de5ff1f5a6d
index: y
internal: n
snippet: y
---

# Listen to logs{#listen-to-logs}

 To register for listening to logs: 
1. Implement a custom class that follows the protocol `PTLogger`:

   ```
   @implementation PTConsoleLogger 
    
   + (PTConsoleLogger *) consoleLogger { 
       return [[[PTConsoleLogger alloc] init] autorelease]; 
   } 
    
   - (void)logEntry:(PTLogEntry *)entry { 
       //Log the message to the console using NSLog  
       NSLog(@"[%@] %@", entry.tag, entry.message); 
   } 
    
   @end
   ```

1. To register the instance to receive logging entries, add an instance of the `PTLogger` to the `PTLoggerFactory`:

   ```
   PTConsoleLogger *logger = [PTConsoleLogger consoleLogger]; 
   // Either use the addLogger method: 
   [[PTLogFactory sharedInstance] addLogger:(logger)] 
    
   //Or replace the preceding line with this macro for ease of use 
   //PTLogAddLogger(logger); 
   
   ```

<a id="example_3738B5A8B4C048D28695E62297CF39E3"></a>

Here is an example of filtering logs by using the `PTLogEntry` type: 

```
@implementation PTConsoleLogger 
 
+ (PTConsoleLogger *) consoleLogger { 
    return [[[PTConsoleLogger alloc] init] autorelease]; 
} 
 
- (id) init { 
    self = [super init]; 
 
    if (self) { 
        self.logLevel = PTLogEntryTypeInfo; 
    } 
 
    return self; 
} 
 
- (void)logEntry:(PTLogEntry *) entry { 
    //Filtering the entry by log level  
    if (entry.type < _logLevel) { 
        return; 
    } 
 
    //Log the message to the console using NSLog NSLog(@"[%@] %@", entry.tag, entry.message); 
} 
 
@end
```


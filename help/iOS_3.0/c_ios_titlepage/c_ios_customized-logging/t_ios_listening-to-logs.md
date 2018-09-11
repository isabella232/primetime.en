---
seo-title: Listening to logs
title: Listening to logs
uuid: f00f742c-1998-4cab-97f1-7aa8508c9b36
index: y
internal: n
snippet: y
translate: y
---

# Listening to logs

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

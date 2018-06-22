---
description: By default, forces an ad break to play when the user seeks over an ad break. You can customize the behavior to skip an ad break if the time elapsed from a previous break completion is within a certain number of minutes.
seo-description: By default, forces an ad break to play when the user seeks over an ad break. You can customize the behavior to skip an ad break if the time elapsed from a previous break completion is within a certain number of minutes.
seo-title: Skip ad breaks for a period of time
title: Skip ad breaks for a period of time
---

# Skip ad breaks for a period of time

>[!IMPORTANT]
>
>When there is an internal seek to skip an ad, here might be a slight pause in the playback.
The following example of a customized ad policy selector skips ads in the next five minutes (wall clock time) after a user has watched an ad break.

>1. Register the policy instance to be used by  through the client factory.
>       
>       ```
>       // Create an instance of the custom policy selector 
>       PTS5MinuteSkipBreakPolicySelector *adPolicySelector 
>        = [[[PTS5MinuteSkipBreakPolicySelector alloc] initWithMediaPlayer:self.player] autorelease]; 
>        
>       // register this instance 
>       [[PTDefaultMediaPlayerClientFactory defaultFactory] registerAdPolicySelector:adPolicySelector];
>       ```
>       
>   
>1. Implement your customization.
>       
>       **PTS5MinuteSkipBreakPolicySelector.h**
>       
>       
>       ```
>       #import "PTMediaPlayerNotifications.h" 
>       #import "PTMediaPlayer.h" 
>       #import "PTDefaultAdPolicySelector.h" 
>        
>       // extend the default policy 
>       selector@interface PTS5MinuteSkipBreakPolicySelector : PTDefaultAdPolicySelector 
>        
>       - (id)initWithMediaPlayer:(PTMediaPlayer *)player; 
>        
>       @end
>       ```
>       
>       **PTS5MinuteSkipBreakPolicySelector.m**
>       
>       
>       ```
>       #import "PTS5MinuteSkipBreakPolicySelector.h" 
>        
>       double MIN_BREAK_INTERVAL = 60 * 5; // 5 minutes 
>        
>       @implementation PTS5MinuteSkipBreakPolicySelector 
>       { 
>        PTMediaPlayer *_player; 
>        NSTimeInterval _lastAdBreakPlayedTime; 
>       } 
>        
>       - (id)initWithMediaPlayer:(PTMediaPlayer *)player 
>       { 
>        if (self = [super init]) 
>        { 
>        _lastAdBreakPlayedTime = 0; 
>        _player = [player retain]; 
>        [self addobservers]; 
>        } 
>        
>        return self; 
>       } 
>        
>       - (NSArray *)selectAdBreaksToPlay:(PTAdPolicyInfo *)info 
>       { 
>        NSLog(@"%@ - selectAdBreaksToPlay (%f): %f", self, 
>        CMTimeGetSeconds(info.currentTime), _lastAdBreakPlayedTime); 
>        
>        BOOL shouldPlay = [self shouldPlayAdBreaks]; 
>        if (shouldPlay) 
>        { 
>        return [super selectAdBreaksToPlay:info]; 
>        } 
>        
>        return nil; 
>       } 
>        
>       - (PTAdBreakPolicyType)selectPolicyForAdBreak:(PTAdPolicyInfo *)info 
>       { 
>        NSLog(@"%@ - selectPolicyForAdBreak (%f): %f %f", self, 
>        CMTimeGetSeconds(info.currentTime), _lastAdBreakPlayedTime, 
>        [[NSDate date] timeIntervalSince1970]); 
>        
>        BOOL shouldPlay = [self shouldPlayAdBreaks]; 
>        if (shouldPlay) 
>        { 
>        return [super selectPolicyForAdBreak:info]; 
>        } 
>        
>        return PTAdBreakPolicyTypeSkip; 
>       } 
>        
>       - (BOOL)shouldPlayAdBreaks 
>       { 
>        NSTimeInterval currentTime = [[NSDate date] timeIntervalSince1970]; 
>        if (_lastAdBreakPlayedTime &lt;= 0) 
>        { 
>        return YES; 
>        } 
>        
>        if (_lastAdBreakPlayedTime &gt; 0 &amp;&amp; (currentTime - _lastAdBreakPlayedTime) &gt; MIN_BREAK_INTERVAL) 
>        { 
>        return YES; 
>        } 
>        
>        // don't play any ad break if 5 minutes hasn't elapsed 
>        return NO; 
>       } 
>        
>       - (void) onMediaPlayerAdBreakStarted:(NSNotification *) notification 
>       { 
>        NSLog(@"%@ - AdBreak Start", self); 
>       } 
>        
>       - (void) onMediaPlayerAdBreakCompleted:(NSNotification *) notification 
>       { 
>        _lastAdBreakPlayedTime = [[NSDate date] timeIntervalSince1970]; 
>        NSLog(@"%@ - AdBreak Complete at: %f", self, _lastAdBreakPlayedTime); 
>       } 
>        
>       - (void)addobservers 
>       { 
>        [[NSNotificationCenter defaultCenter] addObserver:self selector:@selector(onMediaPlayerAdBreakStarted:) 
>        name:PTMediaPlayerAdBreakStartedNotification object:_player]; 
>        [[NSNotificationCenter defaultCenter] addObserver:self selector:@selector(onMediaPlayerAdBreakCompleted:) 
>        name:PTMediaPlayerAdBreakCompletedNotification object:_player]; 
>       } 
>        
>       - (void)removeObservers 
>       { 
>        [[NSNotificationCenter defaultCenter] removeObserver:self]; 
>       } 
>        
>       - (void)dealloc 
>       { 
>        [self removeObservers]; 
>        [_player release]; 
>        [super dealloc]; 
>       } 
>        
>       @end
>       ```
>       
>   
>   

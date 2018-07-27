---
description: The PTMediaPlayer interface encapsulates the functionality and behavior of a media player object.
seo-description: The PTMediaPlayer interface encapsulates the functionality and behavior of a media player object.
seo-title: Set up the PTMediaPlayer
title: Set up the PTMediaPlayer
uuid: 9a81278c-151f-4b02-a7aa-c80ad1ce49a6
index: n
internal: n
snippet: y
translate: y
---

# Set up the PTMediaPlayer

To set up your ` PTMediaPlayer`: 

>1. Fetch the media's URL from your user interface, for example, in a text field.

>    
>       ```
>       NSURL *url = [NSURL URLWithString:textFieldURL.text];
>       ```
>1. Create ` PTMetadata`.
>   Assume that your method ` createMetada` prepares metadata (see  ad-insertion ).>

>    
>       ```
>       PTMetadata *metadata = [self createMetadata]
>       ```
>1. Create ` PTMediaPlayerItem` by using your ` PTMetadata` instance.

>    
>       ```
>       PTMediaPlayerItem *item = [[[PTMediaPlayerItem alloc] 
>              initWithUrl:url mediaId:yourMediaID metadata:metadata] autorelease];
>       ```
>1. Add observers to notifications that  <!-- PH element: phrases/primetime-sdk-name --> dispatches.

>    
>       ```
>       [self addObservers]
>       ```
>1. Create ` PTMediaPlayer` using your new ` PTMediaPlayerItem`.

>    
>       ```
>       PTMediaPlayer *player = [PTMediaPlayer playerWithMediaPlayerItem:item];
>       ```
>1. Set properties on your player.

>       ` PTMediaPlayer`>    
>       ```
>       player.autoPlay                    = YES;  
>       player.closedCaptionDisplayEnabled = YES; 
>       player.videoGravity                = PTMediaPlayerVideoGravityResizeAspect;  
>       player.allowsAirPlayVideo          = YES;
>       ```
>1. Set the player's view property.

>    
>       ```
>       CGRect playerRect = self.adPlayerView.frame;  
>       playerRect.origin = CGPointMake(0, 0); 
>       playerRect.size = CGSizeMake(self.adPlayerView.frame.size.width,  
>                                    self.adPlayerView.frame.size.height); 
>        
>       [player.view setFrame:playerRect]; 
>       [player.view setAutoresizingMask:  
>             ( UIViewAutoresizingFlexibleWidth | UIViewAutoresizingFlexibleHeight )];
>       ```
>1. Add the player's view in the current view's subview.

>    
>       ```
>       [self.adPlayerView  setAutoresizesSubviews:YES];  
>       [self.adPlayerView addSubview:(UIView *)player.view];
>       ```
>1. Call ` play` to start media playback.

>    
>       ```
>       [player play];
>       ```

---
description: The CCManager handles the display and visibility of the closed captions, along with procuring the tracks from the and assigning those tracks to the selected media item.
seo-description: The CCManager handles the display and visibility of the closed captions, along with procuring the tracks from the and assigning those tracks to the selected media item.
seo-title: Displaying the closed captions
title: Displaying the closed captions
---

# Displaying the closed captions

Set display and visibility options by editing CCManager.java.

>1. Get the array of closed captioning in string format.
>   ```java
>   /** 
>    * Get the array of closed captioning in string format. Each of them 
>    * concatenates with a given label. 
>    * 
>    * @param label 
>    * the label to be 
>    * @return an array of String each represents the closed captioning track 
>    */ 
>    
>    @Override 
>    public List &lt;String&gt; getCCsAsArray(String label) { 
>    List&lt;String&gt; closedCaptionsTracksAsStrings = new ArrayList&lt;String&gt;(); 
>    MediaPlayerItem currentItem = mediaPlayer.getCurrentItem(); 
>    if (currentItem != null) { 
>    List&lt;ClosedCaptionsTrack&gt; closedCaptionsTracks = currentItem 
>    .getClosedCaptionsTracks(); 
>    Iterator&lt;ClosedCaptionsTrack&gt; iterator = closedCaptionsTracks 
>    .iterator(); 
>    while (iterator.hasNext()) { 
>    ClosedCaptionsTrack closedCaptionsTrack = iterator.next(); 
>    String isActive = closedCaptionsTrack.isActive() ? " (" + label 
>    + ")" : ""; 
>    if(!(closedCaptionsTrack.getLanguage().isEmpty()) || !(isActive.isEmpty()) ) 
>    { 
>    closedCaptionsTracksAsStrings.add(closedCaptionsTrack.getName() 
>    + " : " + closedCaptionsTrack.getLanguage() + isActive); 
>    } 
>    } 
>    } 
>    
>    return closedCaptionsTracksAsStrings; 
>    //.toArray(new String[closedCaptionsTracksAsStrings.size()]); 
>    } 
>    
>   
>   ```
>   
>   
>1. Show the closed captioning tracks in a log.
>   ```
>   /** 
>    * Show the closed captioning tracks in log 
>    */ 
>    private void showClosedCaptions() { 
>    List&lt;ClosedCaptionsTrack&gt; closedCaptionsTracks = mediaPlayer 
>    .getCurrentItem().getClosedCaptionsTracks(); 
>    
>    Iterator&lt;ClosedCaptionsTrack&gt; iterator = closedCaptionsTracks 
>    .iterator(); 
>    while (iterator.hasNext()) { 
>    ClosedCaptionsTrack track = iterator.next(); 
>    Player.logger.i(LOG_TAG + "#", "CC track: " + track.getName() 
>    + ". Has activity: " + track.isActive() + "."); 
>    } 
>    }
>   ```
>   
>   
>1. Determine if there is closed caption information and filter the inactive closed captions and map the index based on language.
>   ```
>   >    /** 
>    * Determine closed captioning visibility from config 
>    * 
>    * @return Visibility.VISIBLE if CC visibility is set to true in the config, 
>    * Visibility.INVISIBLE otherwise 
>    */ 
>    private MediaPlayer.Visibility getClosedCaptionVisibilityPref() { 
>    return ccConfig.getCCVisibility() ? MediaPlayer.Visibility.VISIBLE 
>    : MediaPlayer.Visibility.INVISIBLE; 
>    } 
>    
>   // method to Filter the inactive closed captions and map the index based on the language 
>   // to get the appropriate track. 
>    
>    public void selectClosedCaptionsFiltered(String language, int indexFiltered) { 
>    MediaPlayerItem currentItem = mediaPlayer.getCurrentItem(); 
>    int index = 0; 
>    if (!language.isEmpty()) { 
>    if(!language.equalsIgnoreCase("None")) { 
>    List&lt;ClosedCaptionsTrack&gt; closedCaptionsTracks = currentItem 
>    .getClosedCaptionsTracks(); 
>    
>    for (int i = 0; i&lt;closedCaptionsTracks.size(); i++) { 
>    ClosedCaptionsTrack closedCaptionTrackObj = closedCaptionsTracks.get(i); 
>    if (language.contains(closedCaptionTrackObj.getName())) { 
>    index = i; 
>    setSelectedClosedCaptionsIndex(indexFiltered); 
>    break; 
>    } 
>    } 
>    ClosedCaptionsTrack desiredClosedCaptionsTrack = currentItem 
>    .getClosedCaptionsTracks().get(index); 
>    boolean result = currentItem 
>    .selectClosedCaptionsTrack(desiredClosedCaptionsTrack); 
>    if (result) { 
>    updateClosedCaptionsVisibility(); 
>    } 
>    } 
>    else { 
>    setSelectedClosedCaptionsIndex(indexFiltered); 
>    mediaPlayer.setCCVisibility(MediaPlayer.Visibility.INVISIBLE); 
>    } 
>    } 
>    }
>   ```
>   
>   
>   

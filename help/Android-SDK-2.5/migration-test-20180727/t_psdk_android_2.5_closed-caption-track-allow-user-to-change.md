---
description: This procedure is an example of how to create a button that allows a user to select a closed caption track.
seo-description: This procedure is an example of how to create a button that allows a user to select a closed caption track.
seo-title: Allow users to change the caption track
title: Allow users to change the caption track
uuid: 464a9b43-3888-499d-85d5-92924e436a02
index: n
internal: n
snippet: y
translate: y
---

# Allow users to change the caption track


>1. Create a button to change the closed caption track.
>
>   ```
>   xml>   &lt;Button 
>     android:id="@+id/selectCC" 
>     android:layout_width="wrap_content" 
>     android:layout_height="wrap_content" 
>     android:layout_alignParentBottom="true" 
>     android:layout_alignParentRight="true" 
>     android:layout_marginRight="10dp" 
>     android:onClick="selectClosedCaptioningClick" 
>     android:text="CC" /&gt; 
>   
>   ```
>
>1. Convert the list of available closed caption tracks to a string array.
>   The closed caption tracks that have activity, that is, channels for which  <!-- PH element: phrases/primetime-sdk-name --> has discovered data, are marked accordingly.
>
>   ```
>   java>   /** 
>   * Converts the closed captions tracks to a string array. 
>   * 
>   * @return array of CC tracks 
>   */ 
>   private String[] getCCsAsArray() { 
>       List&lt;String&gt; closedCaptionsTracksAsStrings = new ArrayList&lt;String&gt;(); 
>       MediaPlayerItem currentItem = mediaPlayer.getCurrentItem(); 
>       if (currentItem != null) { 
>           List&lt;ClosedCaptionsTrack&gt; closedCaptionsTracks = 
>           currentItem.getClosedCaptionsTracks(); 
>           Iterator&lt;ClosedCaptionsTrack&gt; iterator = closedCaptionsTracks.iterator(); 
>           while (iterator.hasNext()) { 
>               ClosedCaptionsTrack closedCaptionsTrack = iterator.next(); 
>               String isActive = closedCaptionsTrack.isActive() ? " (" +  
>                 getString(R.string.active)+ ")" : ""; 
>               closedCaptionsTracksAsStrings.add(closedCaptionsTrack.getName() +  
>                 isActive); 
>           } 
>       } 
>       return closedCaptionsTracksAsStrings. 
>         toArray(new String[closedCaptionsTracksAsStrings.size()]); 
>   } 
>   
>   ```
>
>1. When the user clicks the button, display a dialog that lists all the default closed caption tracks.
>
>   ```
>   java>   public void selectClosedCaptioningClick(View view) { 
>       Log.i(LOG_TAG + "#selectClosedCaptions", "Displaying closed captions chooser dialog."); 
>       final String items[] = getCCsAsArray(); 
>       final AlertDialog.Builder ab = new AlertDialog.Builder(this); 
>       ab.setTitle(R.string.PlayerControlCCDialogTitle); 
>       ab.setSingleChoiceItems(items, selectedClosedCaptionsIndex, new DialogInterface.OnClickListener() { 
>           public void onClick(DialogInterface dialog, int whichButton) { 
>               // Select the new closed captioning track. 
>               MediaPlayerItem currentItem = mediaPlayer.getCurrentItem(); 
>               ClosedCaptionsTrack desiredClosedCaptionsTrack =  
>                 currentItem.getClosedCaptionsTracks().get(whichButton); 
>               boolean result = currentItem.selectClosedCaptionsTrack(desiredClosedCaptionsTrack); 
>               if (result) { 
>                   selectedClosedCaptionsIndex = whichButton; 
>               } 
>               // Dismiss dialog. 
>               dialog.cancel(); 
>        } 
>       }).setNegativeButton(R.string.PlayerControlCCDialogCancel, new DialogInterface.OnClickListener() { 
>           public void onClick(DialogInterface dialog, int whichButton) { 
>               // Just cancel the dialog. 
>           } 
>       }); 
>       ab.show(); 
>   } 
>   
>   ```
>

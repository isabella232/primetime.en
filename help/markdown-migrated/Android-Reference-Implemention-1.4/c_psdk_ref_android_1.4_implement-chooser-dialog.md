---
description: You can implement a chooser dialog that allows the user to select the desired closed captions or no closed captions.
seo-description: You can implement a chooser dialog that allows the user to select the desired closed captions or no closed captions.
seo-title: Implement a chooser dialog
title: Implement a chooser dialog
---

# Implement a chooser dialog

The following code sample illustrates how the reference implementation implements a chooser dialog:
```java
/** 
 * Displays a chooser dialog, allowing the user to select the desired closed 
 * captions. 
 */ 
private void displayClosedCaptioningDialog() { 
 Player.logger.i(LOG_TAG + "#selectClosedCaptions", "Displaying closed captions chooser dialog."); 
 final List&lt;String&gt; items = ccManager.getClosedCaptionTracks(getActivity().getString(R.string.active)); 
 
 //Adding the option of having "none" for user convenience 
 
 items.add(0, "None"); 
 
 final String[] charItems = items.toArray(new String[items.size()]); 
 
 final AlertDialog.Builder ab = new AlertDialog.Builder(getActivity()); 
 ab.setTitle(R.string.PlayerControlCCDialogTitle); 
 ab.setSingleChoiceItems(charItems, 
 ccManager.getSelectedClosedCaptionsIndex()+1, 
 new DialogInterface.OnClickListener() { 
 public void onClick(DialogInterface dialog, int index) { 
 // Select the new closed captioning track. 
 ccManager.selectClosedCaptionTrack(index-1); 
 } 
 } 
} 

```


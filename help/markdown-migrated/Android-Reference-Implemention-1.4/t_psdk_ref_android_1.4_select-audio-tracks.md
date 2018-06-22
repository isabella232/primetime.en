---
seo-title: Select the audio tracks
title: Select the audio tracks
---

# Select the audio tracks

<table id="table_4900A45C80AE41F1B0BFCB18FA1C4427"> 
 <tgroup cols="2"> 
  <colspec colnum="1" colname="col1" colwidth="1.00*" /> 
  <colspec colnum="2" colname="col2" colwidth="2.96*" /> 
  <thead> 
   <tr> 
    <th colname="col1" class="entry"> To... </th> 
    <th colname="col2" class="entry"> Call... </th> 
   </tr> 
  </thead> 
  <tbody> 
   <tr> 
    <td colname="col1"> Get a list of available AA tracks </td> 
    <td colname="col2"> <a href="http://help.adobe.com/en_US/primetime/reference_implementation/android/javadoc/com/adobe/primetime/reference/manager/AAManager.html#getAudioTracks()" scope="external" format="html"> getAudioTracks() </a> </td> 
   </tr> 
   <tr> 
    <td colname="col1"> Get the current selected track </td> 
    <td colname="col2"> <a href="http://help.adobe.com/en_US/primetime/reference_implementation/android/javadoc/com/adobe/primetime/reference/manager/AAManager.html#getSelectedAudioTrack()" format="html" scope="external"> getSelectedAudioTrack() </a> </td> 
   </tr> 
   <tr> 
    <td colname="col1"> Select an AA track </td> 
    <td colname="col2"> <a href="http://help.adobe.com/en_US/primetime/reference_implementation/android/javadoc/com/adobe/primetime/reference/manager/AAManager.html#selectAlternateAudioTrack(int)" format="html" scope="external"> selectAlternateAudioTrack() </a> </td> 
   </tr> 
  </tbody> 
 </tgroup> 
</table>

To select audio tracks for late-binding audio, implement [ IAAConfig ](http://help.adobe.com/en_US/primetime/reference_implementation/android/javadoc/com/adobe/primetime/reference/config/IAAConfig.html).

The following code sample illustrates how the reference implementation gets the audio tracks from the  and assigns the selected track to the associated media item:

```java
/** 
 * Displays a chooser dialog, allowing the user to select the desired 
 * alternate audio track. 
 */ 
private void displayAlternateAudioDialog() { 
 PrimetimeReference.logger.i(LOG_TAG + "#selectAlternateAudio", 
 "Displaying alternate audio chooser dialog."); 
 final int selectedAlternateAudio = aaManager.getSelectedAudioTrackIndex(); 
 if (selectedAlternateAudio != AAManagerOn.INVALID_AUDIO_TRACK) { 
 final String items[] = aaManager.getAudioTracks(); 
 new AlertDialog.Builder(getActivity()) 
 .setTitle(R.string.PlayerControlAADialogTitle) 
 .setSingleChoiceItems(items, selectedAlternateAudio, 
 new DialogInterface.OnClickListener() { 
 public void onClick(DialogInterface dialog, int whichButton) { 
 boolean result = 
 aaManager.selectAlternateAudioTrack(whichButton); 
 if (result) { 
 PrimetimeReference.logger.i(LOG_TAG 
 + "#selectAlternateAudio", 
 "Audio track selection successful"); 
 } else { 
 PrimetimeReference.logger.i(LOG_TAG 
 + "#selectAlternateAudio", 
 "Audio track selection failed"); 
 } 
 // Dismiss dialog. 
 dialog.cancel(); 
 } 
 }).setNegativeButton(R.string.PlayerControlCCDialogCancel, 
 new DialogInterface.OnClickListener() { 
 public void onClick(DialogInterface dialog, 
 int whichButton) { 
 // Just cancel the dialog. 
 } 
 }).show(); 
 
 } else { 
 PrimetimeReference.logger.i(LOG_TAG + "#selectAlternateAudioFailed", 
 "Unable to detect the currently selected audio track."); 
 Toast.makeText(getActivity(), 
 "Unable to detect the currently selected audio track", 
 Toast.LENGTH_SHORT).show(); 
 } 
} 

```
>   1.
>   
>   

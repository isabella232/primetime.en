---
seo-title: Configure adaptive bit rates using ABRControlParametersBuilder
title: Configure adaptive bit rates using ABRControlParametersBuilder
uuid: f008ac46-b757-4ba9-a215-ca6f14d02f1d
index: n
internal: n
snippet: y
translate: y
---

# Configure adaptive bit rates using ABRControlParametersBuilder

Using the ` ABRControlParametersBuilder` helper class is the simplest, most efficient way to set ABR parameters. 
* The ` ABRControlParametersBuilder` constructor sets all of the ABR parameters to default values on the underlying ` ABRControlParameters` object.
* You can reset individual ABR parameters during run time, as long as you maintain a reference to the same ` ABRControlParametersBuilder` instance.
This class also includes the ` toABRControlParameters()` helper method. Use this method to get an instance of ` ABRControlParameters` and set it on the ` mediaPlayer.ABRControlParameters` property. This causes your settings to go into effect in the player. 

>1. Instantiate the ` ABRControlParametersBuilder` helper class, and set the parameters on the Media Player.
>   For example, the following sample initializes all parameters to the defaults, then sets only the policy to conservative, and restricts the maximum bit rate to 1000000:>
>   ```
>   var abrBuilder:ABRControlParametersBuilder =  
>     new ABRControlParametersBuilder(); 
>   abrBuilder.policy = ABRControlParameters.CONSERVATIVE_POLICY; 
>   abrBuilder.maxBitRate = 1000000; 
>   mediaPlayer.abrControlParameters =  
>     abrBuilder.toABRControlParameters();
>   ```
>
>1. Modify individual ABR parameters at run time.
>   To modify individual parameters while leaving the rest of the parameters as they were:>
>   ```
>   // If later you want to reset the max bit rate to 2000000 
>   abrBuilder.maxBitRate = 2000000; 
>   mediaPlayer.abrControlParameters =  
>     abrBuilder.toABRControlParameters();
>   ```
>   To retain your previous settings, you must maintain a reference to the same ` ABRControlParametersBuilder` instance you created in Step 1.>

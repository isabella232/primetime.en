---
seo-title: Configure adaptive bit rates using ABRControlParametersBuilder
title: Configure adaptive bit rates using ABRControlParametersBuilder
---

# Configure adaptive bit rates using ABRControlParametersBuilder

Using the`codeph  ABRControlParametersBuilder` helper class is the simplest, most efficient way to set ABR parameters.
* The `codeph  ABRControlParametersBuilder` constructor sets all of the ABR parameters to default values on the underlying `codeph  ABRControlParameters` object.
* You can reset individual ABR parameters during run time, as long as you maintain a reference to the same `codeph  ABRControlParametersBuilder` instance.
This class also includes the `codeph  toABRControlParameters()` helper method. Use this method to get an instance of `codeph  ABRControlParameters` and set it on the `codeph  mediaPlayer.ABRControlParameters` property. This causes your settings to go into effect in the player.

>1. Instantiate the `codeph  ABRControlParametersBuilder` helper class, and set the parameters on the Media Player.
>   For example, the following sample initializes all parameters to the defaults, then sets only the policy to conservative, and restricts the maximum bit rate to 1000000:
>   ```
>   var abrBuilder:ABRControlParametersBuilder = 
>    new ABRControlParametersBuilder(); 
>   abrBuilder.policy = ABRControlParameters.CONSERVATIVE_POLICY; 
>   abrBuilder.maxBitRate = 1000000; 
>   mediaPlayer.abrControlParameters = 
>    abrBuilder.toABRControlParameters();
>   ```
>   
>   
>1. Modify individual ABR parameters at run time.
>   To modify individual parameters while leaving the rest of the parameters as they were:
>   ```
>   // If later you want to reset the max bit rate to 2000000 
>   abrBuilder.maxBitRate = 2000000; 
>   mediaPlayer.abrControlParameters = 
>    abrBuilder.toABRControlParameters();
>   ```
>   To retain your previous settings, you must maintain a reference to the same`codeph  ABRControlParametersBuilder` instance you created in Step 1.
>   
>   

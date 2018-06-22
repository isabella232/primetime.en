---
description: You can set ABR control values only with ABRControlParameters, but you can construct a new one at any time.
seo-description: You can set ABR control values only with ABRControlParameters, but you can construct a new one at any time.
seo-title: Configure adaptive bit rates using ABRControlParameters
title: Configure adaptive bit rates using ABRControlParameters
---

# Configure adaptive bit rates using ABRControlParameters

This ability to set ABR parameters was supported before the existence of the `codeph  ABRControlParametersBuilder` class, but this ability is still effective for setting ABR parameters at construction time. However, to change individual parameters after construction, you should use the `codeph  ABRControlParametersBuilder` class.

The following conditions apply to `codeph  ABRControlParameters`:
* You must provide values for all parameters at construction time.
* You cannot change individual values after construction time.
* If the parameters that you specify are outside of the allowed range, an `codeph  ArgumentError` is thrown.

>1. Decide on initial, minimum, and maximum bit rates.
>   
>1. Determine the ABR policy:
>   
>* `codeph  CONSERVATIVE_POLICY`
>* `codeph  MODERATE_POLICY`
>* `codeph  AGGRESSIVE_POLICY`
>   
>   
>   
>1. Set the ABR parameter values in the `codeph  ABRControlParameters` constructor and assign them to the Media Player.
>   ```
>   mediaPlayer.abrControlParameters = new ABRControlParameters( 
>    ABRControlParameters.CONSERVATIVE_POLICY, 
>    0, // Initial bit rate 
>    0, // Minimum bit rate 
>    1000000 // Maximum bit rate 
>   );
>   ```
>   
>   
>   

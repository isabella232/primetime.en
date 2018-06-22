---
seo-title: Enable or disable QoS statistics reporting
title: Enable or disable QoS statistics reporting
---

# Enable or disable QoS statistics reporting

>1. Create a QosManager or enable QoS reporting using the ManagerFactory.
>    * To create a QosManager:
>      ```
>      // This application needs to use the advertising workflow feature 
>      QoSManager qosManager = new QosManagerOn();
>      ```
>      
>    * To use a ManagerFactory to enable the display of QoS statistics:
>      ```
>      qosManager = ManagerFactory.getQosManager( 
<b>true</b>, config, mediaPlayer);
>      ```
>      >[!NOTE]
>      >
>      >Changing the boolean to`codeph  false` disables QoS reporting.
>      
>   
>1. Add event listeners:
>   ```
>   qosManager.addEventListener(qosManagerEventListener);
>   ```
>   
>   
>1. Create the QoS provider and attach it to the player activity context:
>   ```
>   qosManager.createQOSProvider(getActivity());
>   ```
>   
>   
>   

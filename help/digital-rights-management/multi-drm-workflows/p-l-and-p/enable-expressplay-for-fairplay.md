---
description: The FairPlay DRM solution from Apple requires some setup when you use it with the ExpressPlay DRM services. This involves obtaining credentials from Apple and uploading them to ExpressPlay.
seo-description: The FairPlay DRM solution from Apple requires some setup when you use it with the ExpressPlay DRM services. This involves obtaining credentials from Apple and uploading them to ExpressPlay.
seo-title: Enable ExpressPlay service for FairPlay
title: Enable ExpressPlay service for FairPlay
uuid: 0fa8e857-88e2-413d-b086-27c9a5461e9c
---

# Enable ExpressPlay service for FairPlay{#enable-expressplay-service-for-fairplay}

The FairPlay DRM solution from Apple requires some setup when you use it with the ExpressPlay DRM services. This involves obtaining credentials from Apple and uploading them to ExpressPlay.

Follow these steps to enable ExpressPlay service for FairPlay content protection. 

1. Obtain credentials from Apple.

   These credentials are provisioned uniquely to each service provider. You must request them by completing the following form: [https://developer.apple.com/contact/fps/](https://developer.apple.com/contact/fps/). 

   >[!NOTE]
   >
   >Select **[!UICONTROL Content Provider]** for Primary Role.

   Once your request is approved, Apple will send you a *FairPlay Streaming Deployment Package*.
1. Generate a Certificate Signing Request.

       You can use [!DNL openssl] to generate your public/private key pair, and your certificate signed request (CSR).

    1. Generate your key pair.     
    
       ```    
       openssl genrsa -aes256 -out privatekey.pem 1024 
       ```    
    
    1. Generate your CSR.     
    
       ```    
       openssl req -new -sha1 -key privatekey.pem -out certreq.csr  
         -subj "/CN=SubjectName /OU=OrganizationalUnit /O=Organization /C=US"
       ```

       >[!NOTE]
       >
       >The instructions for this step are located in your *FairPlay Streaming Deployment Package*, but are included here for your convenience. If you have issues with this part of the process, check the instructions in *FairPlayCertificateCreation.pdf* (in your deployment package).

1. Upload your CSR through the Apple developer portal.
   1. The Team Agent for your development team must log into [!DNL developer.apple.com/account].
   1. Click on **[!UICONTROL Certificates, Identifiers & Profiles]**, then select the **[!UICONTROL iOS, tvOS, watchOS]** drop-down on the upper left of the page, then click on **[!UICONTROL Certificates->Production]** on the left of the page.
   1. Click the **[!UICONTROL +]** button on the upper right of the page to request a new certificate. Select the **[!UICONTROL FairPlay Streaming Certificate]** option under **[!UICONTROL Production]**.
   
      The *Add iOS Certificate* dialog opens.   
   1. In the *Add iOS Certificate*, upload the CSR file you generated in Step 2.b., and click **[!UICONTROL Generate]**.
   
      Your Application Secret Key (ASK) is displayed in the same dialog.   
   1. Write down your ASK, and store it in a safe location.
   1. Key in your ASK to complete certificate generation and click **[!UICONTROL Continue]**.
   1. After you verify that you have saved your ASK, click **[!UICONTROL Generate]** to continue.

      >[!NOTE] {importance="high"}
      >
      >It is important that you save a copy of your ASK and store it securely. *If your ASK is compromised, you will no longer be able to protect your content with FairPlay Streaming.* Only one (1) ASK is allocated to your team. The value will not be provided again and you cannot retrieve it at a later time.

   1. Download your FPS Certificate.
   
      Be sure to save a backup copy of your private key (from Step 2.a.) and your public key (the FPS Certificate you downloaded in this step) in a safe place.   
1. Set up your ExpressPlay account with your FairPlay credentials.
   1. Let's say the certificate name you downloaded in Step 3.h. is [!DNL fairplay.cer].
   1. Open the [!DNL fairplay.cer] file with the Apple Keychain Access utility.
   1. Filter your many certificates by entering " `fairplay`" in the search field located up on the top right.
   1. Identify your company's FairPlay certificate.
   
      Your company name should be associated with the certificate issued by Apple.   
   1. Expand the certificate by selecting the expand arrow, and right-click on your private key.
   1. Select **[!UICONTROL Export "Your Company Name"]** and save the [!DNL .p12] file.
   
      You will be asked to assign a password to secure this file. Make a note of this password as you will need to send this with your credentials package.   
   1. Login to your account on [www.expressplay.com](https://www.expressplay.com).
   1. Click **[!UICONTROL DRM SERVICES]** on the upper left, then select the **[!UICONTROL FairPlay]** tab.
   1. Upload your FairPlay credentials to your ExpressPlay account.

       1. Create a text file that contains the value of your ASK (this should be 32 characters, for example: `1234567890abcdef1234567890abcdef`), and select this file for upload. 
       1. Select the PKCS12 file from Step 4.f. for upload. 
       1. Enter the PKCS12 file password from Step 4.f. 
       1. Click the Upload button.

>Now you can create iOS applications or HTML5 pages with FairPlay content protection along with your [!DNL fairplay.cer] certificate using the ExpressPlay service for FairPlay. >
><!--<a id="fig_sjr_2pn_sv"></a>-->
>![](assets/multi_drm_expressplay_drm_services_web.png)>

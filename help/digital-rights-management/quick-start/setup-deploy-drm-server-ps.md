---
seo-title: Set up and deploy the server for Protected Streaming
title: Set up and deploy the server for Protected Streaming
uuid: 300a1b63-0bf0-48a8-977d-212563025c19
index: y
internal: n
snippet: y
---

# Set up and deploy the server for Protected Streaming{#set-up-and-deploy-the-server-for-protected-streaming}

1. Set up the configuration folder on the Primetime DRM DVD:

[!DNL \Adobe Access Server for Protected Streaming\configs\].
   1. Copy the sample [!DNL configs] folder to your [!DNL <Tomcat_installation_dir>] and rename the copied folder to [!DNL licenseserver].
   
      The path to the configs folder should now be [!DNL <Tomcat_install_dir>\licenseserver\].   
   1. Run [!DNL Scrambler.bat] to obtain the encrypted passwords for the transport and license server PFX files in the Primetime DRM<DVD> [!DNL \Adobe Access Server for Protected Streaming\] directory:

       * `Scrambler.bat <Adobe-provided transport credential password>` 
       * `Scrambler.bat <Adobe-provided license server credential password>`

   1. Copy the PFX files to the [!DNL <TomcatInstallDir>\licenseserver\flashaccessserver\tenants\<tenant-name>\] directory.
   1. Edit the corresponding tenant configuration in [!DNL <TomcatInstallDir>\licenseserver\flashaccessserver\tenants\sampletenant\flashaccess-tenant.xml], with the following settings:

      ```   
      Configuration|Tenant|Credentials|TransportCredential|File|path=<filename-transport-credential-PFX> 
      Configuration|Tenant|Credentials|TransportCredential|File|password=<scrambled-transportcredential-password> 
      Configuration|Tenant|Credentials|LicenseServerCredential|File|path=<fielname-license-servercredential-PFX> 
      Configuration|Tenant|Credentials|LicenseServerCredential|File|password=<scrambled-license-servercredential-password>
      ```

1. Run the [!DNL Validator.bat] utility to verify configuration is valid:

   ```
   Validator.bat -g -r <absolute-path-to TomcatInstallDir\licenseserver>
   ```

1. Copy the [!DNL flashaccessserver.war] file from the CD to the [!DNL <TomcatInstallDir>\webapps\] directory.
1. If Tomcat is running, stop the running Tomcat instance by pressing `<CTRL-C>` in the command window (if it was launched from the command window). You can also stop the server from the Windows Services application if Tomcat was installed as a Windows Service.
1. To start Tomcat, enter the following command:

   ```
   <TomcatInstallDir>\bin\catalina run
   ```

1. To verify the set up, enter the following URL in a browser:

   ```
    https://<LicenseServer>:8080/flashaccessserver/flashaccess/license/v2
   ```


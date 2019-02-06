---
seo-title: Preparing passwords for the Server properties files
title: Preparing passwords for the Server properties files
uuid: 2d876eb0-b1a5-4c30-ae96-0a22f6a03910
---

# Preparing passwords for the Server properties files {#preparing-passwords-for-the-server-properties-files}

To ensure the security of your credential’s password, a tool is provided to encrypt the password before it is entered into the [!DNL flashaccess-refimpl.properties] or [!DNL flashaccess-refimpl-packager.properties] file.

To run the tool using the ANT script provided:

* Go to *`<Reference Implementation Server Path>`* [!DNL \refimpl] 

* Ensure the `sdkdir` property in [!DNL build-refimpl.xml] points to the directory containing the Adobe Access SDK 
* Run the following command using ANT:

  ```
      ant -f build-refimpl.xml
  ```

* When prompted, type your credential’s password

To run the tool using Java:

* Go to *`<Reference Implementation Server Path>`*\ [!DNL scrambler] 

* From the command prompt, enter the command:

* On Windows:

    ```    
    java -classpath path_to_adobe-flashaccess-sdk.jar;.  
    com.adobe.flashaccess.refimpl.util.ScrambleUtil your_pfx_password
    ```

* On Linux:

    ```    
        java -classpath path_to_adobe-flashaccess-sdk.jar;.  
        com.adobe.flashaccess.refimpl.util.ScrambleUtil your_pfx_password
    ```

The utility outputs the encrypted password, which you must copy to the .properties file.

>[!NOTE]
>
>Passwords encoded using the password scrambling utility provided with the reference implementation will not work with the Adobe Access Server for Protected Streaming.

---
seo-title: Update the License Server WAR File
title: Update the License Server WAR File
uuid: 7a51dcce-4af4-4f32-94b8-8553dbe06cc7
index: y
internal: n
snippet: y
---

# Update the License Server WAR File{#update-the-license-server-war-file}

In order to support clients that have individualized via an On Premises Individualization server, you must update the License Server’s certificate root of trust to include the newly acquired Individualization CA credential. A Python script ( [!DNL addIndivCert.py]) is included in the [!DNL update_license_server] folder.

Do the following to update the License Server: 

1. Make a copy of the WAR files to be updated (examples: [!DNL flashaccess.war], [!DNL faxsks.war]).
1. Make sure the WAR files are unlocked and have their permissions set so they can be modified.
1. Run the [!DNL addIndivCert.py] Python script to update the License Server WAR files.

       The inputs for the script are as follows:

    * `cert`: PKCS12 file containing the Individualization CA certificate 
    * `war`: WAR file to be updated

   The output file is an updated WAR file.

<a id="example_2618EBFFC4664D35B9CC68D74197BDC3"></a>

```
./addIndivCert.py -cert NEW_IndivCA.cer -war flashaccess.war
```

The WAR files will be modified in place. If necessary, you can edit the Python script to suit your particular needs. After you perform the updates, you can deploy the WAR files normally. 

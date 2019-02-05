---
seo-title: Command line configuration file
title: Command line configuration file
uuid: c2376f7b-56a7-46f3-9693-10cfbb762a91
---

# Command line configuration file

{#command-line-configuration-file}

Several of the command-line tools require a configuration file that contains information for the tools to use for applying policies and encrypting files.

The default configuration file is [!DNL flashaccesstools.properties]. It is located in the working directory; that is, the directory from which you run the tools (see [Installing the command line tools](../../aaxs-reference-implementations/command-line-tools/installing-the-command-line-tools.md). Each tool also contains an option ( `-c`) that lets you point to the configuration file you want to use if you prefer not to use the default.

The configuration file uses the Java property file format. If values for any of the properties contain special characters, keep in mind the following restrictions:

* Escape backslashes with an additional backslash. For example, to specify the [!DNL C:\credentials.pfx] file, specify it as [!DNL C:\\credentials.pfx] or [!DNL C:/credentials.pfx]. To specify a file on a network server, specify [!DNL \\\\server\\folder\\filename.pfx]. 
* The configuration file can contain only Latin-1 characters. If you must use non-Latin-1 characters, use the appropriate Unicode escape sequence (using, optionally, the [!DNL native2ascii] tool that comes with Java).

Set values for properties in the configuration file before you run the tools. For some of the command line tools, you can set the values for some options through either the command line or the configuration file. In those cases, values that are set through the command line take precedence over any values in the configuration file. 

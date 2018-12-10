---
seo-title: Command line tool requirements
title: Command line tool requirements
uuid: 27be6b7a-bae8-4b7b-9387-530bd9bb2f81
index: y
internal: n
snippet: y
---

# Command line tool requirements{#command-line-tool-requirements}

The requirements for using the command line tools available in the reference implementations are as follows:

* All of the command line tools require Java 1.5 or higher. 
* Packager and License Server credentials (certificate and password) that are issued by Adobe. You need credentials to encrypt and sign video files, to sign Policy Update and Revocation lists, and to pre-generate licenses.

>[!NOTE] {class="- topic/note "}
>
>Because of a Java bug, arguments that are used on the command line (such as file names, policy names, or descriptions) must use only characters from the operating system's default character set.


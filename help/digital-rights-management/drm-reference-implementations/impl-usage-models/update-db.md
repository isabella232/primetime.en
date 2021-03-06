---
seo-title: Update the reference implementation DB
title: Update the reference implementation DB
uuid: 2883045e-ad62-466d-94a2-fc45ded2a4f5
---

# Update the reference implementation DB{#update-the-reference-implementation-db}

To control usage models under which a license is issued to a designated user, add entries to the reference implementation database. 

1. Add entries to the `Customer` table.

   The `Customer` table includes user names and passwords to authenticate users. It also indicates whether a user has a subscription (a license that is issued under the *Subscription* usage model). 

1. Grant a user access under the Download-to-own or Video-on-demand usage models.

       Add entries to the `CustomerAuthorization` table to specify:

    * The usage model 
    * Each segment of content that a user can access

For more information on how to populate each table, see the [!DNL PopulateSampleDB.sql] script (included on your Primetime DRM DVD in the [!DNL Reference Implementation/Server/Reference Implementation Server/dbscript/] directory). 

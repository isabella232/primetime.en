---
description: You can choose a custom starting point for when to enter a DVR stream instead of the default behavior of entering the DVR stream at the beginning using the ConfigProvider class.
seo-description: You can choose a custom starting point for when to enter a DVR stream instead of the default behavior of entering the DVR stream at the beginning using the ConfigProvider class.
seo-title: Choosing a custom starting point for DVR
title: Choosing a custom starting point for DVR
uuid: a7e13865-2b86-4234-ac4c-9a5320b293db
---

# Choosing a custom starting point for DVR {#choosing-a-custom-starting-point-for-dvr}

You can choose a custom starting point for when to enter a DVR stream instead of the default behavior of entering the DVR stream at the beginning using the ConfigProvider class.

To set the start time through the ConfigProvider class: 

1. Enable isCustomPositionPrefEnabled().
1. Set the start time in retrieveStartTimePref().
1. Check that the custom start position is enabled.

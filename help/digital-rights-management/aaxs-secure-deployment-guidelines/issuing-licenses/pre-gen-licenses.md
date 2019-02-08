---
seo-title: Pre-generating licenses
title: Pre-generating licenses
uuid: 0207abdf-52bb-4bd0-a4f2-fe740b89fa83
---

# Pre-generating licenses{#pre-generating-licenses}

If you are pre-generating licenses that contain time-based usage rules, it is highly recommended that the license includes synchronization requirements (See *Using the Adobe Access SDK for Protecting Content* guide), so the license expiration can be enforced securely. Implementing a ‘heart beat' mechanism between the client and the server is highly recommended if you have any time-based restrictions in the license, since the heart beat will synchronize the client time with the server time. 

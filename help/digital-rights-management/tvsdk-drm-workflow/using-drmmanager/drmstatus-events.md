---
seo-title: Handling DRMStatus Events
title: Handling DRMStatus Events
uuid: f1509acf-21f1-4739-889d-9de2da6acd80
index: y
internal: n
snippet: y
---

# Handling DRMStatus Events{#handling-drmstatus-events}

The `DRMManager` dispatches a `DRMStatusEvent` object after a call to the `loadVoucher()` method completes successfully. If a license is obtained, then the detail property of the event object has the value: `DRM.voucherObtained`, and the voucher property contains the `DRMVoucher` object. If a license is not obtained, then the detail property still has the value: `DRM.voucherObtained`; however, the voucher property is null. A license cannot be obtained if, for example, you use the `LoadVoucherSetting` of `localOnly` and there is no locally cached license. If the `loadVoucher()` call does not complete successfully, perhaps because of an authentication or communication error, then the `DRMManager` dispatches a `DRMErrorEvent` or `DRMAuthenticationErrorEvent` object instead. 

---
description: The Entitlement Manager is the feature manager that supports the implementation.
seo-description: The Entitlement Manager is the feature manager that supports the implementation.
seo-title: Entitlement Manager Overview
title: Entitlement Manager Overview
---

# Entitlement Manager Overview

**Feature Overview**

The  integration with the Android Primetime SDK Reference Implementation adds a new feature manager to the application. However, unlike many of the other feature managers, *the EntitlementManager is used in several places throughout the application*. The following provides an overview of the changes and additions made to the Reference Implementation to support :

  *
  **EntitlementManager class**
  
  The `codeph EntitlementManager` class handles all the communication with the  SDK, plus encapsulates the application logic required for the entitlement workflows. The `codeph EntitlementManager`'s public API is used by the application to initiate entitlement workflows, while the `codeph EntitlementMangerListener` interface provides a callback mechanism for the application to handle `codeph EntitlementManger` events.
  
  
  *
  **EntitlementManger callbacks**
  
  The Reference Implementation's main activity, the `codeph CatalogActivity`, creates an instance of `codeph EntitlementManagerListener` and registers it with the `codeph EntitlementManager`. In this way, the `codeph EntitlementManager` may signal needed UI updates to the rest of the application. The callbacks include displaying/hiding a loading dialog, displaying status dialogs, updating authorization and authentication icons, and starting video playback upon successful authorization.
  
  
  *
  **Entitlement Dialogs**
  
  The `codeph EntitlementDialogFragment` class generates dialog messages based on the entitlement status passed to the class constructor. This class is used for authentication success messages as well as all error messages. The `codeph CatalogActivity` displays the entitlement dialogs when it receives specific events from the `codeph EntitlementManager`. In addition, the `codeph CatalogActivity` implements the `codeph EntitlementDialogListener` interface, which includes callback methods to signal when a dialog is closed or when the user logs out from the  service.
  
  
  *
  **Content Provider Selection and Login**
  
  During authentication with , two new activities, `codeph MvpdPickerActivity` and `codeph MvpdLoginActivity`, allow the user to select their content provider and login. Both of these activities are started from the `codeph CatalogActivity` via the `codeph EntitlementManager`. Additionally, both the `codeph MvpdPickerActivity` and `codeph MvpdLoginActivity` return results to the `codeph CatalogActivity` and therefor the `codeph CatalogActivity` must override the `codeph Activity.onActivityResult` method.
  
  
  *
  **Sign In button**
  
  The Reference Implementation's main activity, the `codeph CatalogActivity`, includes a new "Sign In" button in its action bar. The Sign In button allows the user to initiate authentication with . Additionally, the user may initiate authentication by selecting a protected video for playback. The Sign In button's icon and text changes depending on the user's authentication status, and the `codeph CatalogActivity` contains code to update the button's icon and text when the page refreshes. To do this, when the `codeph CatalogActivity` starts, it calls `codeph EntitlementManager.checkAuthentication()` to update the user's authentication status.
  
  
  *
  **Content entitlement**
  
  Within the `codeph CatalogView`, new icons are displayed on top of the content's icon to signal the user's authorization status for that content. For example, if the user is pre-authorized to view a video, then a green circle icon is displayed over the content. However, if the user is not pre-authorized to view the video, a key icon is displayed. The display of these icons is handled in `codeph ContentTileAdapter`, however the update of their state is initiated from the `codeph CatalogActivity` when a callback in the `codeph EntitlementManagerListener` is called.
  
  
  *
  **Content Playback**
  
  Video playback now requires an authorization check by the `codeph EntitlementManager`. The call to `codeph EntitlementManager.getAuthorization()` occurs within `codeph CatalogView`. If the video requires authorization and the user is authorized, the `codeph PlayerActivity` is started from the `codeph CatalogActivity`.
  
  

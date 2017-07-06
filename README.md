# android-M-RuntimePermissions
This permissionsUtils handle (Activity/Fragment) how to check and request  runtime permissions available in Android M and above

## Introduction

Android M introduced runtime permissions. Applications targeting M and above need to request their permissions at runtime. All permissions still need to be declared in the AndroidManifest. However, when accessing APIs that require a permission, the Activity or Fragment has to verify that the permission has been granted or request the missing permissions using calls through the support library. Permissions are checked through ActivityCompat#checkSelfPermission(Context, String) or ContextCompat#checkSelfPermission(Context, String). Permission are requested through ActivityCompat#requestPermissions(Activity, String[], int), and the response received in a callback to ActivityCompat.OnRequestPermissionsResultCallback#onRequestPermissionsResult(int, String[], int[]). Applications can provide an additional rational for the use of permissions after calling ActivityCompat#shouldShowRequestPermissionRationale(Activity,String). This call will return true if the application should provide the user with more context on why the requested permissions is needed, for example if the permission request has been denied before.

If an application targets an SDK below M, all permissions are granted at runtime and are available when the application is running. The support library calls handle these checks appropriately. However, if permissions have been turned off in the system settings for an application targeting an SDK below M, the API will return empty or no data.


## Pre-requisites

Android SDK 23+

Android Build Tools v23+

targetSdkVersion 23+

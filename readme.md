## Sample - AppServiceWPF

# Description
This sample demonstrates how to package a WPF Client app with a Windows App Service (in proc).

# Note

The restricted capability (**extendedBackgroundTaskTime**) is needed due to the architecture of the WPF Client and how it interfaces with the Windows app service. 
This is because when Win32 apps (like WPF Client) connect to a Windows App Service, it is given 30 seconds to run. In contrast to UWP clients when have no maximum run time.
The solution for this scenario is to include the extendedBackgroundTaskTime capability in the app manifest. This removes to 30 second run-time restriction allowing our solution to run as expected. When an app with this architecture to the Microsoft Store, a waiver will need to be requested since **extendedBackgroundTaskTime** is a restricted capability.

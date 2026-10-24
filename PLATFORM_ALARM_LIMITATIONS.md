# Alarm reliability: important platform note

The supplied WakeTask project is a browser/PWA prototype. Its alarm scheduler is a JavaScript interval in the active page. It can notify/ring while the page is running, but it cannot reliably wake the device or run a mission when the browser is fully closed, the phone is locked, or the operating system suspends the page. A service worker alone cannot guarantee exact-time alarm playback.

For dependable Android alarms, a native Android/Capacitor implementation still needs to be added and tested. At minimum it must schedule native alarms, request notification and (where required) exact-alarm permissions, play the chosen sound in a native alarm activity/service or notification flow, handle reboot/time-zone/time changes, and explain battery/background restrictions. It must also define how a user enters the mission screen from the alarm notification. Force-stop, revoked permissions, Do Not Disturb, manufacturer battery restrictions, and OS policies can still affect behavior.

No Android Studio project, Gradle wrapper, signing configuration, or Windows Electron project was present in the supplied ZIP. This update therefore includes no claimed APK or Windows installer.

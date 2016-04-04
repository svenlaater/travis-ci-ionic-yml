# Headless Ionic/Android continuos integration setup on Travis CI

An example configuration of Ionic/cordova + NPM + AngularJS + Bower + gulp + Android continuous integration setup on Travis CI and headless APK build for Android.

## Headless signing of release.apk

1) Create `release-signing.properties`.

```
storeFile=MyApp.keystore
keyAlias=MyApp
storePassword=<pwd>
keyPassword=<pwd>
```

3) `$ ionic build android --release`

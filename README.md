# Headless Ionic/Android continuos integration setup on Travis CI

An example configuration of Ionic/cordova + NPM + AngularJS + Bower + gulp continuous integration setup and headless APK build for Android on [Travis CI](https://travis-ci.com/)

## Headless signing of release.apk

1) Create `release-signing.properties`.

```
storeFile=MyApp.keystore
keyAlias=MyApp
storePassword=<pwd>
keyPassword=<pwd>
```

3) `$ ionic build android --release`

# Headless Ionic/Android continuous integration setup on Travis CI

An example configuration of Ionic/cordova + NPM + AngularJS + Bower + gulp continuous integration setup and headless APK build for Android on [Travis CI](https://travis-ci.com/)

## Headless signing of release.apk

1) Create build.json as explained in  [cordova docs](https://cordova.apache.org/docs/en/latest/guide/platforms/android/#using-buildjson)

2) `$ cordova build android --release`

Same for iOS

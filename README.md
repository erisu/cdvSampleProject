# Example Cordova Project Git Structure

## What is Important To Commit to Repo

### Cordova Related Files

* www/
* config.xml
* package.json

### Others

* package-lock.json
* .gitignore

## Checkout and Build

```bash
git clone <repo>
cd <repo-name>
npm i

$ cordova prepare

Discovered platform "electron" in config.xml or package.json. Adding it to the project
Using cordova-fetch for cordova-electron@^1.0.0
Adding electron project...
Creating Cordova project for cordova-electron:
	Path: /tmp/cdvSampleProject/platforms/electron
	Name: HelloCordova
Discovered platform "android" in config.xml or package.json. Adding it to the project
Using cordova-fetch for cordova-android@^8.0.0
Adding android project...
Creating Cordova project for the Android platform:
	Path: platforms/android
	Package: io.cordova.hellocordova
	Name: HelloCordova
	Activity: MainActivity
	Android target: android-28
Subproject Path: CordovaLib
Subproject Path: app
Android project created with cordova-android@8.1.0
Discovered saved plugin "cordova-plugin-whitelist". Adding it to the project
Installing "cordova-plugin-whitelist" for android
Installing "cordova-plugin-whitelist" for electron
Discovered saved plugin "cordova-plugin-inappbrowser". Adding it to the project
Installing "cordova-plugin-inappbrowser" for android
Installing "cordova-plugin-inappbrowser" for electron
Discovered saved plugin "cordova-plugin-device". Adding it to the project
Installing "cordova-plugin-device" for android
Installing "cordova-plugin-device" for electron
```

## Summary

* Prepare output from the step above shows that the platforms and plugins are discovered and being added to the project
* All plugins and platforms are stored in `package.json` as `devDependencies`
* Running `cordova build electron` does not readd packages to `dependencies`
* Plugin `cordova-plugin-whitelist` which is default to `config.xml` can be removed once it is in `package.json`

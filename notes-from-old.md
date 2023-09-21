![image](https://github.com/TheSafetyNet/safety-net/assets/8891185/09e594c6-e7ef-4109-b4cb-b384d77ae9a3)

![image](https://github.com/TheSafetyNet/safety-net/assets/8891185/84dbb2e1-e18a-407f-b0bb-614428ec7fb7)

# AgoraPolis
An open marketplace for security.
com.fractalstrategies.polis

## Dev -> Build
- `react-native run-android`
- increment `./android/app/build.gradle`, `package.json`
- `react-native run-android --variant=release`
- Test on physical device
- Upload APK to Google Play
- `git status`
- update Tasks
- `git add . && git commit -m 'add & update icons' && git push`


## Development
Do not use Expo. We're over that now. Use `npx react-native` or `react-native-cli`.
### React Native / Metro
- `react-native run-android`
- `react-native run-ios`
- `react-native doctor`


## Build
### Debug
- `react-native run-android`
- Check ./android/app/build/outputs/apk/debug/
### Release
- `react-native run-android --variant=release`
- Check ./android/app/build/outputs/apk/release/


## npm packages
Install these using `npm i -s <package-name>`
- @react-navigation/native @react-navigation/stack @react-navigation/bottom-tabs
- @react-native-firebase/app @react-native-firebase/auth @react-native-firebase/firestore
<--- 2020-08-12 - AH
- react-native-svg @fortawesome/fontawesome-svg-core @fortawesome/free-solid-svg-icons @fortawesome/react-native-fontawesome
- react-native-maps
- react-native-screens react-native-safe-area-context react-native-gesture-handler @react-native-community/masked-view
<--- 2020-08-13 - AH
- react-native-splash-screen
<--- 2020-08-14 - AH
- react-native-reanimated
- @react-native-community/async-storage
- react-native-reanimated@alpha
Install these using `yarn add <package-name>`
- yarn add react-native-reanimated@alpha
Others / Unused
- maybe: react-native-svg-transformer


## Create New API Signing Key
- Docs: https://reactnative.dev/docs/signed-apk-android
- Keystore filename: polis-keystore.jks
- Key Alias: polis-key
- Keystore Pass: polis keystore password
- Not used: Key Pass: polis key password
- `keytool -genkey -v -keystore polis-keystore.jks -alias polis-key -keyalg RSA -keysize 2048 -validity 10000`
- polis keystore password, Alexander Mandelbrot, Engineering, Fractal Strategies, Chicago, IL, US, yes
### Update
- ./.gitignore
- ./android/gradle.properties
- ./android/app/build.gradle


## First Steps
- Install Node.js
- Install Android Studio
- Create a new AVD
- `npx react-native init Polis`
- create new signing key
- update `./android/gradle.properties`
- update `./android/build.gradle`
- install packages
- connect Firebase
- copy icons
- `react-native run-android`


## Firebase
- https://console.firebase.google.com/u/1/
- Create project
- Download `google-services.json`
- Cloud Firestore location: nam5 (us-central)
- match /database/{database}/documents
- `firebase.initializeApp()`
- Docs: https://rnfirebase.io/firestore/usage


## Design
### Navigation
- https://reactnavigation.org/docs/navigation-context
### Activities
- Main (first screen to appear when the user launches the app)
- Monitor
- SearchMarket
- ProvideService
- Preferences
- SelectPhoto
- ViewMessages
- ViewMessage
- WriteMessage
### Colors
- https://reactnative.dev/docs/colors
### Icons
- https://fontawesome.com/icons?d=gallery
### Dev Cycle
1. Add a new feature
2. Test on local emulator
3. Test APK 'release' build
4. Push changes
### Philosophies
- Must be 
- Code, Test, Build, Repeat
- Quick iteration
- No errors, no warnings
- Close/restart often
- Build frequently
- Commit & push frequently
- Write tests
- Successfully build at beginning and end of a dev session

1. A: Always
2. B: Be
3. C: Coding

fractalstrategies@gmail.com
http://fractalstrategies.com/


## Philosophies
- Quick iteration
- Build frequently
- Commit & push frequently
- Write tests
- Successfully build at beginning and end of a dev session

## To Do
- Review App build process
- Update App Icon
- Update spash screen

## Test Locally
Run `npx react-native run-android`
Opens new terminal window to run Metro package launcher
Bundles and runs in emulator

## Build APK (Android)
- Run `cd android && ./gradlew assembleRelease && cd ..`
- Check `./android/app/build/outputs/apk/release/`

## Build AAB
- `cd android && ./gradlew bundleRelease && cd ..`

## Build Notes
- Look inside `./android` or `./ios`
- Check `build.gradle` file

Use <highlight>AgoraPolis</highlight> to find or provide help to your neighbors

# AgoraPolis


## Start Dev
- `expo start --android`
- Close/restart often
- No errors, no warnings
- `git add . && git commit -m '' && git push`


## Build
- increment `app.json`: version, versionCode, buildNumber
- `git add . && git commit -m '' && git push`
- `expo build:android -t app-bundle`
- download `aab` file and upload to Google Play


## To Do
- Fix Icon fonts
- Add Native Map
- Descriptions and tips
- Refactor Provide icons
- Review React Navigation https://reactnavigation.org/docs/getting-started && https://reactnavigation.org/docs/tab-based-navigation/#a-stack-navigator-for-each-tab 
- Review Internal Test track https://support.google.com/googleplay/android-developer/answer/3131213
- Install APK as a trusted developer - Pending publication, waiting for review
- Review Build steps https://expo.io/dashboard/asifhazrat/builds/ca6e6fa1-7c32-4eb6-ac2f-c784cca0c63e/logs
- Agorist maxims splash
- Bare workflow https://docs.expo.io/bare/exploring-bare-workflow/
- Output web bundle
- Add Firebase https://docs.expo.io/guides/setup-native-firebase/
- Add basic Q&A
- Add Feedback mechanism
- Remove unnecessary permissions
- Review Google Play Shop https://play.google.com/store/apps/dev?id=6018649271647208244
- Dev vs Prod https://docs.expo.io/workflow/development-mode/#development-mode
- CI CD https://docs.expo.io/guides/setting-up-continuous-integration/
- Review app.json https://docs.expo.io/versions/latest/config/app/
- Review Gradle Daemon https://docs.gradle.org/current/userguide/gradle_daemon.html
- Create fresh Gradle build https://guides.gradle.org/creating-new-gradle-builds/
- Learn TypeScript https://learnxinyminutes.com/docs/typescript/
- Generate relevant text https://www.digitaltrends.com/features/openai-gpt-3-text-generation-ai/


## Development
There are a few ways to go about development.
Expo is easier, and good for a first run.
Metro is more direct, and closer to production.
### Metro
#### Android
- `npx react-native doctor`
- Start AVD
- `npx react-native run-android`
#### Web
- Run `npx react-native start --port 19001`
- ??? Reload from Metro on device
### New Tab
- Update `types.tsx`
- Update `navigation/BottomTabNavigator.tsx`


## Build
### Android Packaged Kit (APK)
- Run `touch -p android/build.gradle`
- Run `touch -p android/app/src/AndroidManifest.xml`
- Run `cd android && ./gradlew assembleRelease && cd ..`
- Check `./android/app/build/outputs/apk/release/`
### Android App Bundle (AAB)
- `cd android && ./gradlew bundleRelease && cd ..`
### Notes
- Look inside `./android` or `./ios`
- Check `build.gradle` file


## Design
### Colors
- https://reactnative.dev/docs/colors
### Icons
- See https://icons.expo.fyi/


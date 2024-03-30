```
npx react-native@latest init react_native_app
```

This is a new [**React Native**](https://reactnative.dev) project, bootstrapped using [`@react-native-community/cli`](https://github.com/react-native-community/cli).

```
               ######                ######
             ###     ####        ####     ###
            ##          ###    ###          ##
            ##             ####             ##
            ##             ####             ##
            ##           ##    ##           ##
            ##         ###      ###         ##
             ##  ########################  ##
          ######    ###            ###    ######
      ###     ##    ##              ##    ##     ###
   ###         ## ###      ####      ### ##         ###
  ##           ####      ########      ####           ##
 ##             ###     ##########     ###             ##
  ##           ####      ########      ####           ##
   ###         ## ###      ####      ### ##         ###
      ###     ##    ##              ##    ##     ###
          ######    ###            ###    ######
             ##  ########################  ##
            ##         ###      ###         ##
            ##           ##    ##           ##
            ##             ####             ##
            ##             ####             ##
            ##          ###    ###          ##
             ###     ####        ####     ###
               ######                ######


                  Welcome to React Native!
                 Learn once, write anywhere

✔ Downloading template
✔ Copying template
✔ Dependencies installation skipped


info 💡 To enable automatic CocoaPods installation when building for iOS you can create react-native.config.js with automaticPodsInstallation field.
For more details, see https://github.com/react-native-community/cli/blob/main/docs/projects.md#projectiosautomaticpodsinstallation

✔ New project is already inside of a Git repo, skipping git init.


  Run instructions for Android:
    • Have an Android emulator running (quickest way to get started), or a device connected.
    • cd "/Users/user/Desktop/ReactNative0.72/react_native_app" && npx react-native run-android

  Run instructions for iOS:
    • cd "/Users/user/Desktop/ReactNative0.72/react_native_app/ios"

    • Install Cocoapods
      • bundle install # you need to run this only once in your project.
      • bundle exec pod install
      • cd ..

    • npx react-native run-ios
    - or -
    • Open react_native_app/ios/react_native_app.xcodeproj in Xcode or run "xed -b ios"
    • Hit the Run button

  Run instructions for macOS:
    • See https://aka.ms/ReactNativeGuideMacOS for the latest up-to-date instructions.
```

# Getting Started

> **Note**: Make sure you have completed the [React Native - Environment Setup](https://reactnative.dev/docs/environment-setup) instructions till "Creating a new application" step, before proceeding.

## Step 1: Start the Metro Server

First, you will need to start **Metro**, the JavaScript _bundler_ that ships _with_ React Native.

To start Metro, run the following command from the _root_ of your React Native project:

```bash
# using npm
npm start

# OR using Yarn
yarn start
```

## Step 2: Start your Application

Let Metro Bundler run in its _own_ terminal. Open a _new_ terminal from the _root_ of your React Native project. Run the following command to start your _Android_ or _iOS_ app:

### For Android

```bash
# using npm
npm run android

# OR using Yarn
yarn android
```

### For iOS

```bash
# using npm
npm run ios

# OR using Yarn
yarn ios
```

If everything is set up _correctly_, you should see your new app running in your _Android Emulator_ or _iOS Simulator_ shortly provided you have set up your emulator/simulator correctly.

This is one way to run your app — you can also run it directly from within Android Studio and Xcode respectively.

## Step 3: Modifying your App

Now that you have successfully run the app, let's modify it.

1. Open `App.tsx` in your text editor of choice and edit some lines.
2. For **Android**: Press the <kbd>R</kbd> key twice or select **"Reload"** from the **Developer Menu** (<kbd>Ctrl</kbd> + <kbd>M</kbd> (on Window and Linux) or <kbd>Cmd ⌘</kbd> + <kbd>M</kbd> (on macOS)) to see your changes!

   For **iOS**: Hit <kbd>Cmd ⌘</kbd> + <kbd>R</kbd> in your iOS Simulator to reload the app and see your changes!

## Congratulations! :tada:

You've successfully run and modified your React Native App. :partying_face:

### Now what?

- If you want to add this new React Native code to an existing application, check out the [Integration guide](https://reactnative.dev/docs/integration-with-existing-apps).
- If you're curious to learn more about React Native, check out the [Introduction to React Native](https://reactnative.dev/docs/getting-started).

# Troubleshooting

If you can't get this to work, see the [Troubleshooting](https://reactnative.dev/docs/troubleshooting) page.

# Learn More

To learn more about React Native, take a look at the following resources:

- [React Native Website](https://reactnative.dev) - learn more about React Native.
- [Getting Started](https://reactnative.dev/docs/environment-setup) - an **overview** of React Native and how setup your environment.
- [Learn the Basics](https://reactnative.dev/docs/getting-started) - a **guided tour** of the React Native **basics**.
- [Blog](https://reactnative.dev/blog) - read the latest official React Native **Blog** posts.
- [`@facebook/react-native`](https://github.com/facebook/react-native) - the Open Source; GitHub **repository** for React Native.

[README.md#Guides](https://github.com/reactwg/react-native-new-architecture/blob/main/README.md#Guides)

# Enable the New Architecture for Apps

This page will help you create or migrate a React Native app that uses the New Architecture.

> [!WARNING]
> If you're using Expo or plan to use Expo, you can't enable the New Architecture at the moment and will have to wait for a future release of the Expo SDK.

### Prerequisites

1. Use or upgrade to the latest React Native version. This guide is written with the expectation that you’re using the [**latest** React Native release](https://github.com/facebook/react-native/releases/latest).
2. If you previously installed a global `react-native-cli` package, please remove it as it may cause unexpected issues:

```shell
  npm uninstall -g react-native-cli @react-native-community/cli
```

3. Enable Hermes. If you are using React Native 0.70 or above, it is already the [default JS engine](https://reactnative.dev/blog/2022/07/08/hermes-as-the-default) so no action is needed.

### Create a React Native app

If you are creating a new app to enable the New Architecture, follow all the steps in [Setting up the development environment](https://reactnative.dev/docs/environment-setup) section under the **React Native CLI Quickstart** tab.

If following the setup guide, stop when you reach the section **Running your React Native Application**, and resume following this guide.

Then, create a new React Native project from the template:

```shell
npx react-native@latest init AwesomeProject --skip-install
cd AwesomeProject
yarn install
```

### Enable New Architecture for iOS

#### For new apps created from React Native CLI

Navigate to the `ios` directory and run the following:

```shell
# from `ios` directory
bundle install && RCT_NEW_ARCH_ENABLED=1 bundle exec pod install
```

Then build and run the app as usual:

```shell
yarn ios
```

#### For existing apps

You'll need to reinstall your pods by running `pod install` with the right flag:

```shell
# Run pod install with the flag:
RCT_NEW_ARCH_ENABLED=1 bundle exec pod install
```

#### Troubleshooting

##### Run `pod install` when a dependency with native code changes

You will need to run `pod install` each time a dependency with native code changes. Make this command easier to run by adding it to `scripts` to your project's `package.json` file:

```
  "scripts": {
    "pod-install": "RCT_NEW_ARCH_ENABLED=1 bundle exec pod install"
  }
```

and run it with `yarn pod-install`. Note that `bundle install` does not need to run a second time, as long as the Gemfile has not changed.

##### Use Xcode to rename files in the `ios` folder

Whenever you have to rename some files in the `ios` folder, please **use Xcode to rename them**. This ensure that the file references are updated in the Xcode project as well. You might need to clean the build folder (**Project** → **Clean Build Folder** or <kbd>Cmd ⌘</kbd> + <kbd>Shift ⇪</kbd> + <kbd>K</kbd>) before re-building the app. If the file is renamed outside of Xcode, you may need to click on the old `.m` file reference and Locate the new file.

##### `react-native run-ios` fails

If you see a build failure from `react-native run-ios`, there may be cached files from a previous build with the old architecture. Clean the build cache and try again:

1. Open the project `ios/project.xcworkspace` in Xcode
2. In XCode, choose Product > Clean Build Folder
3. In the project directory, remove the `ios/Podfile.lock` file and `ios/Pods` directory: `rm -rf ios/Podfile.lock ios/Pods`
4. Re-run `yarn pod-install` and `yarn ios`

### Enable the New Architecture on Android

> [!NOTE]
> You may notice longer build times with the New Architecture due to additional step of C++ compilation with the Android NDK. To improve your build time, see [Speeding Up Your Build Phase](https://reactnative.dev/docs/build-speed).

#### For new apps created from React Native CLI

Set the `newArchEnabled` property to `true` by **either**:

- Changing the corresponding line in `android/gradle.properties`
- Setting the environment variable `ORG_GRADLE_PROJECT_newArchEnabled=true`

Then build and run the app as usual:

```shell
yarn android
```

#### For existing apps

You will only need to update your `android/gradle.properties` file as follows:

```diff
# Use this property to enable support to the new architecture.
# This will allow you to use TurboModules and the Fabric render in
# your application. You should enable this flag either if you want
# to write custom TurboModules/Fabric components OR use libraries that
# are providing them.
-newArchEnabled=false
+newArchEnabled=true
```

### Verify the New Architecture is in Use

After you build and run the app when Metro serves the JavaScript bundle, you should see `"fabric": true` in the Metro logs:

<img src="/docs/assets/metro-new-arch.png" alt="Metro shows fabric: true" width="600" />

### [Advanced] Handling custom Native Components

If you followed the previous steps but your app uses some custom Native Components that have not been migrated to the New Architecture completely, you are going to see some reddish/pinkish boxes saying that the component is not compatible with Fabric. This is happening because custom Native Components written for the legacy architecture can't run as-is in the New Architecture.

Starting from **React Native 0.72.0**, we worked on a interoperability layer to let you use legacy components in the New Architecture without having to wait for them to be migrated.

You can read more about the interoperability layer and how to use it [here](https://github.com/reactwg/react-native-new-architecture/discussions/135). Follow the guide to register your components and then rerun your app with the commands with either `npm` or `yarn`

```shell
# To run android
npm/yarn run android

# To run iOS
npm/yarn run ios
```

### Want to Know More?

If you'd like to view the code changes relevant to the New Architecture, take a look at the [upgrade helper from version 0.67.4 to 0.68.0](https://react-native-community.github.io/upgrade-helper/?from=0.67.4&to=0.68.0). Files that were added for the New Architecture are marked with a yellow banner.

---

> [!IMPORTANT]
> This documentation is still experimental and details are subject to changes as we iterate.
> Feel free to share your feedback on this [discussion](https://github.com/reactwg/react-native-new-architecture/discussions/8).
>
> Moreover, it contains **several manual steps**. Please note that this won't be representative of the final developer experience once the New Architecture is stable. We're working on tools, templates and libraries to help you get started fast on the New Architecture, without having to go through the whole setup.

# How to Setup a new Developer Environment for _React Native_

* [How to Setup a new Developer Environment for _React Native_](#how-to-setup-a-new-developer-environment-for-react-native)
  * [1: System Requirements](#1-system-requirements)
  * [2: Installation Instructions](#2-installation-instructions)
    * [2.1: Install Node.js](#21-install-nodejs)
    * [2.2: Installing Android Studio](#22-installing-android-studio)
    * [2.3: Setting up Environment Variables](#23-setting-up-environment-variables)
  * [3: Configuration Steps](#3-configuration-steps)
  * [4: Project Creation](#4-project-creation)
  * [5: Running the Project](#5-running-the-project)
    * [5.1: Running the starter project](#51-running-the-starter-project)
    * [5.2: Getting a fresh project](#52-getting-a-fresh-project)
  * [6: Troubleshooting](#6-troubleshooting)
  * [7: Resources](#7-resources)

## 1: System Requirements

<details>
<summary><ins>Hardware Requirements</ins></summary>

* At least 4**GB** of RAM (8**GB** or more is recommended).
* At least 10**GB** of storage space (_20**GB**_ or more is recommended).
* A modern web browser (such as _**Google** Chrome_, _**Mozilla** Firefox_, or _**Microsoft** Edge_) and access to the internet.
* For Android development
  * An _Android_ smartphone (this is optional, but it will speed-up _Android_ app development by a-lot)
* For iOS development
  * An _**Apple** MacBook Air_ with 8GB RAM, An _**Apple** MacOS_ desktop, or better.
    * This is the most important step for developing on _iOS_ as **_Apple_** is very restrictive on where their operating systems are allowed to run.
  * The _iOS_ simulator in _Xcode_ (This is optional, but recommended for testing and debugging).
    * If you didn't follow the step above, please disregard ALL the steps in this subsection.

</details>

<details>
<summary><ins>Software Requirements</ins></summary>

* _Node.js_ (version 18.0 or newer).
* _Java Development Kit_ (_JDK_) (version 17 or newer).
* _Android Studio_ (if you are developing for Android).
* _Xcode_ (if you are developing for iOS)
* _Gradle_ (Compatible with JDK version 17 or newer).

</details>

## 2: Installation Instructions

### 2.1: Install Node.js

1. Visit the official Node.js website: <https://nodejs.org/>
2. Download the LTS (Long Term Support) version for Windows
3. Run the installer and follow the installation wizard
4. Verify the installation by opening a terminal (or a command prompt) and running:

```sh
node --version
npm --version
```

### 2.2: Installing Android Studio

There are two ways of installing Android Studio on your system.

<details>
<summary><ins>Option 1: Using the Official Android Studio Installer</ins></summary>

1. Visit the official Android Studio [website](https://developer.android.com/studio), and download the installer
2. Run the installer and follow the installation wizard

</details>

<details>
<summary><ins>Option 2: Using the Jetbrains Toolbox App</ins></summary>

1. Download the Jetbrains Toolbox App from the [Jetbrains website](https://www.jetbrains.com/toolbox-app/)
2. Run the installer and follow the installation wizard
3. Open the Jetbrains Toolbox App and search for "Android Studio"
4. Click on the "Install" button to install Android Studio

</details>

After following either option, please do the following to install the Android SDK:

* In Android Studio, go to "Tools" > "SDK Manager"
* In the SDK Platforms tab, select the latest Android version
* In the SDK Tools tab, select:
  * Android SDK Build-Tools
  * Android SDK Platform
  * Intel x86 Emulator Accelerator (HAXM installer)
  * Performance (Android Emulator hypervisor driver)
  * Android Virtual Device
* Click "Apply" to install

### 2.3: Setting up Environment Variables

<details>
<summary><ins>For Windows</ins></summary>

1. Open System Properties (Right-click on "This PC" > Properties > Advanced system settings)
2. Click on "Environment Variables"
3. Under "System variables", click "New" and add:
   * Variable name: ANDROID_HOME
   * Variable value: C:\Users\YOUR_USERNAME\AppData\Local\Android\Sdk
4. Edit the "Path" variable and add:
   * %ANDROID_HOME%\platform-tools
   * %ANDROID_HOME%\emulator
   * %ANDROID_HOME%\tools
   * %ANDROID_HOME%\tools\bin

</details>

<details>
<summary><ins>For MacOS/Linux</ins></summary>

1. Open Terminal on your Mac/Linux
2. Open your shell configuration file (e.g., ~/.bash_profile, ~/.zshrc, or ~/.profile) using a text editor (like `nano`). For example:

    ```sh
    nano ~/.bash_profile # or nano ~/.zshrc
    ```

3. Add the following lines to the file: (Both will work for both bash and zsh)

    ```sh
    export ANDROID_HOME=$HOME/Library/Android/sdk
    export PATH=$PATH:$ANDROID_HOME/emulator
    export PATH=$PATH:$ANDROID_HOME/tools
    export PATH=$PATH:$ANDROID_HOME/tools/bin
    export PATH=$PATH:$ANDROID_HOME/platform-tools
    ```

4. Save the file and close the text editor.
5. Run the following command to apply the changes:

    ```bash
    source ~/.bash_profile # or source ~/.zshrc
    # OR
    exec bash # or exec zsh
    ```

</details>

## 3: Configuration Steps

<!-- For additional information on how to configure your project, please refer to the [React Native Documentation](https://reactnative.dev/docs/environment-setup) -->

When it comes to new projects, you should always generate a new `.editorconfig` file in the root of your project. This will ensure that your project will be configured correctly across all editors. Here is a sample `.editorconfig` file: [.editorconfig](.editorconfig)

Be sure to also install **Prettier**/**DPrint** and **ESLint** extensions in your editor. This will ensure that your code will be formatted correctly and will be checked for errors across all editors.

## 4: Project Creation

Creating a new React Native project is easy! To get started, simply run

```sh
npx create-expo-app@latest
```

Yep, that's it! You're now ready to start developing your **_React Native_** project!

## 5: Running the Project

### 5.1: Running the starter project

1. Install dependencies by running:

    ```sh
    npm install
    ```

2. Start the app by running:

    ```sh
    npx expo start
    ```

3. <details>
    <summary><ins>(Optional)</ins></summary>

      Run the app for each platform using the following commands:

      Run for Android:

      ```sh
      npx expo start --android
      ```

      Run for iOS:

      ```sh
      npx expo start --ios
      ```

      Run for the Web:

      ```sh
      npx expo start --web
      ```

      </details>

### 5.2: Getting a fresh project

When you're ready, run:

```bash
npm run reset-project
```

This command will move the starter code to the `app-example` directory and create a blank `app` directory where you can start developing.

## 6: Troubleshooting

> [!NOTE]
>
> For a more cohesive troubleshooting steps, please see the [_React Native_ troubleshooting documentation](https://reactnative.dev/docs/troubleshooting) and the [_Expo_ troubleshooting documentation](https://docs.expo.dev/troubleshooting/overview/).

Common issues and solutions:

* <span style="color: red">`SDK location not found`</span>: Ensure `ANDROID_HOME` is set correctly

* <span style="color: red">Gradle build failure</span>: Make sure you have the latest SDK tools and build tools installed

* <span style="color: red">Emulator not starting</span>: Verify that virtualization is enabled in your BIOS settings

For more specific issues, consult the official React Native documentation or seek help on Stack Overflow.

Please make sure to follow the trouble shooting steps above before submitting an issue. Nobody likes to troubleshoot issues that have already been solved, it's a waste of time for everyone.

## 7: Resources

1. Additional resources: [Getting started with _React Native_](https://reactnative.dev/docs/getting-started)
2. Additional documentation: [Getting started with _Expo_](https://docs.expo.dev/get-started/create-a-new-app/)

# React(Native) Docs

## Computer Configuration

1. Install [Android Studio](https://developer.android.com/studio)
2. Configure PATH and such :
```bash
$ cd
$ cat .profile
(...)
# set PATH so it includes Android Studio bin if it exists
if [ -d '/usr/local/android-studio/bin' ]
then
	PATH="$PATH:/usr/local/android-studio/bin"
fi

# set PATH to run AVD directly
if [ -d "${HOME}/Android/Sdk" ]
then
	export ANDROID_SDK="${HOME}/Android/Sdk"
	PATH="$PATH:$ANDROID_SDK/emulator:$ANDROID_SDK/tools"
fi
```
3. Install React Native Cli
sudo npm install -g react-native-cli

4. Install expo-cli
sudo npm install -g expo-cli


### Managing the AVDs (Android Virtual Devices)

From command line
If you want to use the command line you'll first need to create the virtual device using avdmanager, located under $ANDROID_HOME/tools/bin/avdmanager like so:

```bash
$ANDROID_HOME/tools/bin/avdmanager create avd --force --name testAVD --abi google_apis/x86_64 --package 'system-images;android-23;google_apis;x86_64'
```
After you created the device to emulate, then you need to open it with emulator, which is located under $ANDROID_HOME/tools/emulator. The command for the previously created device should be something like:


If you already added a device VM you can list them all with
```bash
emulator -list-avds
```

```bash
emulator @testAVD
```
If it crashes saying something like...

[140022905190208]:ERROR:./android/qt/qt_setup.cpp:28:Qt library not found at ../emulator/lib64/qt/lib
Ensure you're running the emulator command inside the $ANDROID_HOME/tools folder, otherwise may not work.



## New Apps

### ReactJS App

```bash
$ npm init react-app my-app
```

### React Native App
```bash
$ npm install -g expo-cli
$ expo init my-app
$ cd my-app/
$ npm start
```

## Run App in AVD

$ react-native run-android

## References

https://medium.com/@Charles_Stover/create-a-react-native-app-on-an-android-emulator-1c0d94f288ae

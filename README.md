# Docker image for NativeScript development

## How to use it
Alias the following command as tns or create a script out of it:

```
docker run -it --rm --privileged -v /dev/bus/usb:/dev/bus/usb -v $PWD:/src esarbanis/tns tns
```

If you go with the scripting solution add $@ at the end to pass all arguments.

## Deploy to your device
Make sure you do not run adb server in your host else run:

```
adb kill-server
```

Alias the following command as adb or create a script out of it:

```
docker run -it --rm --privileged -p 5037:5037 -v /dev/bus/usb:/dev/bus/usb -v $PWD:/src esarbanis/tns adb
```

Again if you go with the scripting solution add $@ at the end to pass all arguments.

Once you have setup your system as described above run the following commands:

```
tns build android
adb install ./platforms/android/build/outputs/apk/<APP_NAME>.apk
```

## Enable Gradle Daemon
Append the following line to <WORK_DIR>/gradle:

```
org.gradle.daemon=true
```
# Drozer Installation and Configuration Guide

## Windows

### Prerequisites
1. **Python**: Ensure Python 2.7.x is installed. Download from [Python.org](https://www.python.org/downloads/release/python-2718/).
2. **Java**: Install the Java Development Kit (JDK) from [Oracle](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).

### Steps
1. **Download Drozer** from [Official Site](https://labs.mwrinfosecurity.com/tools/drozer/).
2. **Open Command Prompt** as Administrator.
3. **Install Drozer**:
    ```sh
    pip install drozer
    ```

4. **Verify Installation**:
    ```sh
    drozer console connect
    ```

## Linux (Ubuntu/Debian-based)

### Prerequisites
1. **Python**: Ensure Python 2.7.x is installed.
2. **Java**: Install the Java Development Kit (JDK):
    ```sh
    sudo apt-get install openjdk-8-jdk
    ```

### Steps
1. **Open Terminal**.
2. **Download Drozer** from [Official Site](https://labs.mwrinfosecurity.com/tools/drozer/).
3. **Install Drozer**:
    ```sh
    pip install drozer
    ```

4. **Verify Installation**:
    ```sh
    drozer console connect
    ```

## Android

### Prerequisites
1. **ADB**: Ensure Android Debug Bridge (ADB) is installed and set up. Download from [Android Developers](https://developer.android.com/studio/releases/platform-tools).
2. **Drozer Agent APK**: Download the Drozer Agent APK from the [Official Site](https://labs.mwrinfosecurity.com/tools/drozer/).

### Steps
1. **Install Drozer Agent** on your Android device:
    ```sh
    adb install drozer-agent.apk
    ```

2. **Open Drozer Agent** on your Android device and start the embedded server.
3. **Forward the port** from your computer to the Android device:
    ```sh
    adb forward tcp:31415 tcp:31415
    ```

## Using Drozer to Execute a Command on an Android App

### Steps
1. **Start Drozer Console**:
    ```sh
    drozer console connect
    ```

2. **List Installed Packages**:
    ```sh
    run app.package.list
    ```

3. **Find Attack Surface** of a specific package:
    ```sh
    run app.package.attacksurface com.target.app
    ```

4. **Exploit Vulnerabilities**:
    - Example: **List All Activities** in the target app:
        ```sh
        run app.activity.info -a com.target.app
        ```
    - Example: **Start an Activity**:
        ```sh
        run app.activity.start --component com.target.app com.target.app.MainActivity
        ```

## Troubleshooting

### Common Issues
1. **Drozer Agent not starting**: Ensure the Drozer Agent APK is installed correctly and the embedded server is started.
2. **Port forwarding issues**: Verify that ADB is properly recognizing your device using:
    ```sh
    adb devices
    ```
3. **Drozer connection issues**: Ensure that the Drozer console is connected to the correct port (31415 by default).

### Useful Commands
- **List connected devices**:
    ```sh
    adb devices
    ```
- **Uninstall Drozer Agent**:
    ```sh
    adb uninstall com.mwr.dz
    ```

### References
- [Drozer Official Documentation](https://labs.mwrinfosecurity.com/tools/drozer/)
- [Drozer GitHub Repository](https://github.com/mwrlabs/drozer)

---

By following the steps above, you should be able to install and configure Drozer on Windows, Linux, and Android, as well as use Drozer to execute commands on an Android app.

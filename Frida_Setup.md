# Frida Installation and Configuration Guide

## Windows

### Prerequisites
1. **Python**: Ensure Python 3.x is installed. Download from [Python.org](https://www.python.org/downloads/).
2. **pip**: Should come installed with Python. If not, install it from [get-pip.py](https://pip.pypa.io/en/stable/installation/).

### Steps
1. **Open Command Prompt** as Administrator.
2. **Install Frida**:
    ```sh
    pip install frida-tools
    ```

3. **Verify Installation**:
    ```sh
    frida --version
    ```

## Linux (Ubuntu/Debian-based)

### Prerequisites
1. **Python**: Ensure Python 3.x is installed.
2. **pip**: Install pip if not already installed:
    ```sh
    sudo apt-get install python3-pip
    ```

### Steps
1. **Open Terminal**.
2. **Install Frida**:
    ```sh
    pip3 install frida-tools
    ```

3. **Verify Installation**:
    ```sh
    frida --version
    ```

## Android

### Prerequisites
1. **ADB**: Ensure Android Debug Bridge (ADB) is installed and set up. Download from [Android Developers](https://developer.android.com/studio/releases/platform-tools).

### Steps
1. **Download Frida Server** for Android from the [official releases page](https://github.com/frida/frida/releases).
2. **Extract and push Frida Server** to your Android device:
    ```sh
    adb push frida-server /data/local/tmp/
    ```

3. **Set executable permissions** on the Frida server:
    ```sh
    adb shell "chmod 755 /data/local/tmp/frida-server"
    ```

4. **Run Frida Server** on your Android device:
    ```sh
    adb shell "/data/local/tmp/frida-server &"
    ```

## Executing a Script on an Android App

### Steps
1. **Create a Frida Script** (`script.js`):
    ```js
    // Example Frida script
    Java.perform(function () {
        console.log("Hello from Frida");
    });
    ```

2. **Find the package name** of the target Android app. You can list running packages using:
    ```sh
    adb shell "pm list packages"
    ```

3. **Execute the script using Frida CLI**:
    ```sh
    frida -U -f com.target.app -l script.js --no-pause
    ```
   - `-U` specifies USB device.
   - `-f com.target.app` specifies the app to be launched.
   - `-l script.js` specifies the script to be loaded.
   - `--no-pause` prevents Frida from pausing the target process before running the script.

## Troubleshooting

### Common Issues
1. **Frida server not starting**: Ensure your Android device is rooted or has proper permissions to run the server.
2. **Frida CLI connection issues**: Verify that ADB is properly recognizing your device using:
    ```sh
    adb devices
    ```
3. **Script errors**: Check the console output for any errors in your script.

### Useful Commands
- **List connected devices**:
    ```sh
    adb devices
    ```
- **Kill Frida server** on Android:
    ```sh
    adb shell "pkill frida-server"
    ```

### References
- [Frida Official Documentation](https://frida.re/docs/home/)
- [Frida GitHub Repository](https://github.com/frida/frida)

---

By following the steps above, you should be able to install and configure Frida on Windows, Linux, and Android, as well as execute scripts on an Android app.

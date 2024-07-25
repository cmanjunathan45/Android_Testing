# JADX 1.5.0 Installation and Usage Guide

## Introduction
JADX is a powerful tool for decompiling Android APK files to Java source code. This guide will walk you through the installation process on different platforms and provide basic usage instructions.

## Installation

### Windows

#### Prerequisites
- **Java Development Kit (JDK)**: Ensure JDK is installed. Download from [Oracle](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html) or use a package manager like [Chocolatey](https://chocolatey.org/).

#### Steps
1. **Download JADX 1.5.0**:
    - Visit the [JADX releases page](https://github.com/skylot/jadx/releases) and download `jadx-1.5.0.zip` from [this link](https://github.com/skylot/jadx/releases/download/v1.5.0/jadx-1.5.0.zip).

2. **Extract the ZIP File**:
    - Extract the downloaded ZIP file to a directory of your choice.

3. **Add JADX to Path (Optional)**:
    - Open `Control Panel > System and Security > System > Advanced system settings`.
    - Click on `Environment Variables`.
    - Under `System variables`, find the `Path` variable, select it, and click `Edit`.
    - Click `New` and add the path to the directory where you extracted JADX.
    - Click `OK` to close all dialogs.

4. **Run JADX**:
    - Open Command Prompt and navigate to the directory where you extracted JADX.
    - Run `jadx-gui` to start the GUI version or `jadx` to use the command line version.

**Or you can just extract the zip and run jadx-gui.bat file which in inside bin folder**

### Linux (Ubuntu/Debian-based)

#### Prerequisites
- **Java Development Kit (JDK)**: Ensure JDK is installed.

    ```sh
    sudo apt-get install openjdk-11-jdk
    ```

#### Steps
1. **Download JADX 1.5.0**:
    - Visit the [JADX releases page](https://github.com/skylot/jadx/releases) and download `jadx-1.5.0.zip` from [this link](https://github.com/skylot/jadx/releases/download/v1.5.0/jadx-1.5.0.zip).

2. **Extract the ZIP File**:
    ```sh
    unzip jadx-1.5.0.zip -d jadx-1.5.0
    ```

3. **Add JADX to Path (Optional)**:
    - Open your `.bashrc` or `.zshrc` file:
        ```sh
        nano ~/.bashrc
        ```
    - Add the following line:
        ```sh
        export PATH=$PATH:/path/to/jadx-1.5.0/bin
        ```
    - Save the file and reload the shell configuration:
        ```sh
        source ~/.bashrc
        ```

4. **Run JADX**:
    - Open Terminal and navigate to the directory where you extracted JADX.
    - Run `./bin/jadx-gui` to start the GUI version or `./bin/jadx` to use the command line version.

### macOS

#### Prerequisites
- **Java Development Kit (JDK)**: Ensure JDK is installed. You can install it using [Homebrew](https://brew.sh/):

    ```sh
    brew install openjdk
    ```

#### Steps
1. **Download JADX 1.5.0**:
    - Visit the [JADX releases page](https://github.com/skylot/jadx/releases) and download `jadx-1.5.0.zip` from [this link](https://github.com/skylot/jadx/releases/download/v1.5.0/jadx-1.5.0.zip).

2. **Extract the ZIP File**:
    - Extract the downloaded ZIP file to a directory of your choice.

3. **Add JADX to Path (Optional)**:
    - Open Terminal and edit your shell configuration file (`.bash_profile`, `.zshrc`, etc.):
        ```sh
        nano ~/.zshrc
        ```
    - Add the following line:
        ```sh
        export PATH=$PATH:/path/to/jadx-1.5.0/bin
        ```
    - Save the file and reload the shell configuration:
        ```sh
        source ~/.zshrc
        ```

4. **Run JADX**:
    - Open Terminal and navigate to the directory where you extracted JADX.
    - Run `jadx-gui` to start the GUI version or `jadx` to use the command line version.

## Usage

### Decompiling an APK with GUI
1. **Open JADX GUI**:
    ```sh
    jadx-gui
    ```
2. **Load APK**:
    - In the GUI, click on `File > Open` and select the APK file you want to decompile.
3. **View Decompiled Code**:
    - Once the APK is loaded, you can navigate through the decompiled source code in the left pane.

### Decompiling an APK with Command Line
1. **Open Terminal/Command Prompt**.
2. **Run JADX**:
    ```sh
    jadx -d /path/to/output/dir /path/to/your.apk
    ```

### Notes
- **Decompiled Code**: The decompiled code might not be perfect and might need manual adjustments for readability and accuracy.
- **Resources**: JADX also extracts resources (e.g., images, XML files) from the APK, which you can find in the output directory.

## References
- [JADX GitHub Repository](https://github.com/skylot/jadx)
- [JADX Documentation](https://github.com/skylot/jadx/wiki)

---

By following these steps, you should be able to install and use JADX 1.5.0 on Windows, Linux, and macOS to decompile Android APK files.

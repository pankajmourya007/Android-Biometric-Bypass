
# Android-Biometric-Bypass

A comprehensive guide and toolset for bypassing biometric authentication mechanisms on Android devices. This project demonstrates the use of various tools and scripts, including a custom script `fingerprint bypass.js`, and explores rooting Android emulators, utilizing tools like Frida, and integrating them into practical workflows.

---

## ⚠️ Disclaimer
This project is intended for educational purposes and ethical research only. Misuse of these tools and techniques may violate laws or policies. Always obtain proper authorization before testing or experimenting with security mechanisms.

---

## Features
- **Custom Script**: `fingerprint bypass.js` to manipulate biometric authentication processes.
- **Rooting Android Emulator**: Using `RootAVD` to enable root access in Android emulators.
- **Frida Integration**: Setting up and using Frida Server for runtime analysis and hooking.

---

## Prerequisites
Before you begin, ensure you have the following:
- A PC with Android Emulator installed (e.g., Android Studio AVD).
- Basic understanding of Android debugging tools and techniques.
- Tools installed:
  - **RootAVD**: Root Android Virtual Devices.
  - **Frida**: Dynamic instrumentation toolkit.

---

## Installation and Setup

### 1. Clone the Repository
  ```  
  git clone https://github.com/pankajmourya007/Android-Biometric-Bypass.git
  cd Android-Biometric-Bypass
  ```

### 2. Root Android Emulator
- Download and set up `RootAVD` from its [GitHub repository](https://github.com/newbit1/rootAVD).
- Follow the instructions provided in the `RootAVD` documentation to enable root access for your emulator.

### 3. Install Frida Server
- Download the appropriate Frida server binary for your Android emulator from the [official Frida repository](https://github.com/frida/frida/releases).
- Push the binary to the emulator:

  ``` 
  adb push frida-server /data/local/tmp/
  ```
- Set the correct permissions and start the server:
  ```
  adb shell "chmod 755 /data/local/tmp/frida-server"
  adb shell "/data/local/tmp/frida-server &"
  ```

### 4. Configure Biometric bypass.js
- Place the `Biometric bypass.js` script in your working directory.
- Modify the script as needed to align with the target application's biometric implementation.

---

## Usage

### Step 1: Launch the Emulator
Start your rooted Android emulator and ensure it is functioning correctly.

### Step 2: Run Frida Server
Verify that Frida Server is running on the emulator:
```
adb shell ps | grep frida
```
### Step 3: Identify the Target Application
Use the following command to list all running processes and find the `package ID` of your target application:
```bash
frida-ps -U
```

To include additional information like installed applications (not just running ones), use:
```bash
frida-ps -Uia
```

Locate the package ID for the target app in the output.

### Step 4: Use Biometric bypass.js
Execute the script using Frida:
```bash
frida -U -f <target_app_package> -l fingerprint bypass.js
```
or
```
frida -U -p <target_app_PID> --load fingerprint bypass.js
```

### Step 5: Analyze and Interact
Monitor the script's output and adjust hooks to bypass biometric checks.

---

## Demonstration

### Video Tutorial
[Watch the video here](https://github.com/pankajmourya007/Android-Biometric-Bypass/blob/main/biometric%20bypass.mp4)

### Sample Output
```plaintext
[+] Hooking biometric authentication methods...
[+] Bypass successful. Returning pre-determined values.
```

---

## Contributing
Contributions are welcome! Please submit pull requests with detailed explanations of changes.

---

## License
This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for more details.

---

## References
- [RootAVD GitHub Repository](https://github.com/mrg666/RootAVD)
- [Frida Official Documentation](https://frida.re)


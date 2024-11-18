# Fingerprint Bypass Demo

This repository demonstrates how biometric fingerprint authentication can be bypassed on a rooted Android device using tools like RootAVD, Frida, and a custom script. It includes a demonstration APK, tools for rooting, and a script for bypassing fingerprint authentication.




```plaintext
Fingerprint-Bypass-Demo/
│
├── scripts/
│   └── fingerprint-bypass.js # Frida script to bypass fingerprint authentication
├── tools/
│   ├── frida-server/         # Frida server binary
│   └── rootAVD/              # RootAVD tool for rooting Android emulator
├── demo/
│   └── FingerprintScanner.apk # APK file for demonstration
├── setup/
│   ├── emulator-root-steps.md # Steps to root the emulator using RootAVD
│   ├── adb-tools/            # ADB and Fastboot tools
│   └── patched-boot.img      # Patched boot image (optional)
└── docs/
    ├── Research_Paper.pdf    # Research paper about the project
    └── Blog_Post.md          # Medium blog draft

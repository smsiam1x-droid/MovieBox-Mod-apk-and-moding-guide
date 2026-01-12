# MovieBox Mod & Modding Guide

A comprehensive resource for the **MovieBox Mod APK**, featuring advanced bypasses for reward systems and a detailed guide on Android application modding. This project demonstrates how to intercept and modify application logic to unlock premium features.

## 🚀 Features

The MovieBox Mod includes several key enhancements designed to streamline the user experience and provide unrestricted access to premium content:

*   **Reward System Bypass**: Successfully bypasses "Watch & Earn" and "Do & Get" mechanisms.
*   **Unlimited Coins**: Allows users to collect an unlimited amount of in-app currency.
*   **Premium Access**: Use collected coins to unlock premium features and accounts within the application.
*   **Ad-Free Experience**: Integrated modifications to remove intrusive advertisements.

## 🛠️ Prerequisites

To replicate this project or understand the underlying modifications, you will need:

*   **MT Manager** (Android) or **APKTool** (PC).
*   The original **MovieBox APK** file.
*   Basic understanding of **Smali Code** and **Hexadecimal** values.

## 👨‍💻 Developer's Guide (Technical Analysis)

This section provides a step-by-step documentation of the logic modifications performed on the application.

*   **Target File**: `classes6.dex`
*   **Target Class**: `yo/k` (Package: `yo`, Class: `k`)

### 1. Bypassing "Watch & Earn" (Video Timer)
**Goal**: Force the app to believe the user has watched 300 minutes of content.
*   **Target Method**: `L()I`
*   **Modification**: Return Hex `0x12c` (Decimal: 300).

```smali
.method public final L()I
    .registers 2
    # Returns 300 minutes
    const/16 v0, 0x12c
    return v0
.end method
```

### 2. Bypassing "Play Games" (Game Timer)
**Goal**: Satisfy the "Play for 30 seconds" condition instantly.
*   **Target Method**: `K()I`
*   **Modification**: Return Hex `0x64` (Decimal: 100 seconds).

```smali
.method public final K()I
    .registers 2
    # Returns 100 seconds
    const/16 v0, 0x64
    return v0
.end method
```

### 3. Bypassing "Watch Ads" (Ad Counter)
**Goal**: Force the ad counter to show 10 ads watched.
*   **Target Method**: `N()I`
*   **Modification**: Return Hex `0xa` (Decimal: 10).

```smali
.method public final N()I
    .registers 2
    # Returns 10 ads
    const/16 v0, 0xa
    return v0
.end method
```

## 📱 User Guide (How to Use)

If you are testing the modified APK, please follow these instructions carefully to ensure the modifications take effect:

1.  **Install**: Install the modified APK on your Android device.
2.  **⚠️ IMPORTANT STEP (Clear Data)**:
    *   Before opening the app for the first time, go to **Settings > Apps > MovieBox**.
    *   Select **Storage** and tap **Clear Data**.
    *   *Note: This removes old logic and cached data stored in the MMKV/cache.*
3.  **Launch**: Open the application.
4.  **Claim**: Navigate to the rewards section. You should see "Claim" buttons enabled for all tasks!

## ❓ Troubleshooting

*   **Issue**: Buttons still say "Go" or "Play".
    *   **Fix**: You likely didn't clear the app data. Uninstall the app, reinstall, and **Clear Data** before opening.
*   **Issue**: App crashing on startup.
    *   **Fix**: Ensure you signed the APK correctly (Auto-sign) after modifying the `classes.dex` file.

## ⚠️ Disclaimer

> This project is for **educational and research purposes only**. Modifying applications may violate the Terms of Service of the original software provider. The developers of this mod are not responsible for any misuse or account bans resulting from the use of these tools. Use at your own risk.

## 🤝 Contributing

Feel free to fork this repository or star ⭐ it if you found this guide helpful for your studies! Contributions are welcome:

1.  Fork the repository.
2.  Create a new branch (`git checkout -b feature/improvement`).
3.  Commit your changes (`git commit -am 'Add new feature'`).
4.  Push to the branch (`git push origin feature/improvement`).
5.  Create a new Pull Request.

## 📜 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---
*Happy Learning! 🎓*

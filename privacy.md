# Privacy Policy

**Noted** — Last updated: May 2026

## Summary

Noted does not collect, transmit, or share any user data. Everything you create in the app stays on your device.

## Data Collection

Noted collects **no data whatsoever**. Specifically:

- No personal information
- No usage analytics or telemetry
- No crash reports
- No advertising identifiers
- No cookies or tracking pixels
- No location data

The app does not have the `INTERNET` permission and is technically incapable of transmitting data off your device.

## Data Storage

All data you create — notes, collections, images, drawings, and voice recordings — is stored locally on your device and encrypted at rest:

- Notes, collections, and drawing data are stored in a database encrypted with AES-256 via SQLCipher
- Images, rendered drawings, and voice recordings are stored as separate files, each encrypted with AES-256-GCM
- Encryption keys are stored in the Android Keystore (hardware-backed on supported devices)

Only you can access your data. There is no account system, no server, and no cloud component.

## Data Sharing

Noted does not share data with any third party. When you use the app's export or share features, you are explicitly choosing to send your own data to a destination of your choice (email, file manager, another app, etc.). Noted never initiates any data transfer on its own.

## Backups

Noted opts out of Android's Auto Backup and device-transfer systems for all sensitive files: the encrypted database, encryption-key material, the PIN hash, stored images and drawings, and voice recordings. Non-sensitive user preferences (such as theme and view mode) may be included in Android system backups.

## Permissions

Noted requests only the minimum permissions required for its features:

- **Microphone** (`RECORD_AUDIO`) — to record voice memos. This permission is requested at the moment you first tap the record button, never on app start. If you deny it, every other feature still works; only voice recording is unavailable. Recorded audio is encrypted on the device and never leaves it.
- **Biometric** (`USE_BIOMETRIC` / `USE_FINGERPRINT`) — to offer fingerprint/face unlock alongside the PIN. These are normal Android permissions that are not prompted for; biometric unlock is used only if you enable it.

To attach a photo, Noted launches your device's existing camera app and receives the resulting picture. Noted does **not** request the Camera permission and never accesses the camera directly.

No other permissions are requested or used.

## Changes

If this policy changes, the updated version will be posted here with a new "Last updated" date.

# Privacy Policy

**Noted** — Last updated: September 2026

## Summary

Noted does not collect, transmit, or share any user data. Everything you create in the app stays on your device unless you export or share it.

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
- By default the encryption keys are protected by the Android Keystore (hardware-backed on supported devices). If you turn on Enhanced Security, they are instead protected by your PIN or password (and, if you turn it on, your biometric), and are cleared from memory, usually within a few minutes after you leave Noted.
- While you take a photo, record audio, import, or export, Noted briefly keeps an unencrypted working copy in its private app storage. It is deleted when that step finishes, or the next time Noted starts if the step was interrupted. A photo left over after an interruption is encrypted the next time Noted starts. Exported files are deleted after you save them. Shared exports are kept for about an hour, since the receiving app may still be reading them, and are deleted the next time Noted is opened after that.

There is no account system, no server, and no cloud component.

## Data Sharing

Noted does not share data with any third party. When you use the app's export or share features, you are explicitly choosing to send your own data to a destination of your choice (email, file manager, another app, etc.). Noted never initiates any data transfer on its own.

Your keyboard is a separate app and sees what you type. Noted asks keyboards not to learn from it (Private input, on by default), but what a keyboard does is covered by its own privacy policy.

## Backups

Noted opts out of Android's Auto Backup and device-transfer systems for all sensitive files: the encrypted database, encryption-key material, the PIN hash, stored images and drawings, and voice recordings. Non-sensitive user preferences (such as theme and view mode) may be included in Android system backups.

## Permissions

Noted keeps permissions to a minimum. The only ones that can touch your content are ones you actively opt into:

- **Microphone** (`RECORD_AUDIO`) — to record voice memos. Android asks you for this the first time you choose to record audio, never on app start, and you can decline. If you deny it, every other feature still works. Only voice recording is unavailable. Recorded audio is encrypted on the device and never leaves it unless you export it.
- **Biometric** (`USE_BIOMETRIC` / `USE_FINGERPRINT`) — to offer fingerprint unlock (or face unlock, on devices whose face sensor meets Android's strongest biometric class) alongside your PIN or password. These are normal Android permissions granted at install, so there is no separate prompt. Biometric unlock only takes effect if you turn it on yourself.

Noted also carries four **normal (non-sensitive) permissions** that are added automatically by standard Android libraries it depends on — chiefly the background-scheduling library (WorkManager) behind the optional home-screen Quick Note widget. These are granted at install, are never prompted for, and there is nothing for you to opt into. None of them can read your notes or send data anywhere:

- `WAKE_LOCK`, `RECEIVE_BOOT_COMPLETED`, and `FOREGROUND_SERVICE` — let that library schedule and run its background work.
- `ACCESS_NETWORK_STATE` — lets it check whether a network connection exists. This does **not** grant the ability to use the network: Noted still has no `INTERNET` permission and remains incapable of transmitting data off your device.

To attach a photo, Noted launches your device's existing camera app and receives the resulting picture. Noted does **not** request the Camera permission and never accesses the camera directly. The only remaining entry is a private signature permission Android uses internally to keep Noted's own components from being triggered by other apps. It grants no access to your data or to any device feature.

No other permissions are requested or used.

## Retention and Deletion

Your data stays on your device until you delete it. Deleting an entry or collection removes it and its attachments from Noted. Uninstalling Noted or clearing its app storage permanently deletes all of its data and keys. Noted keeps no copy anywhere else.

## Changes

If this policy changes, the updated version will be posted here with a new "Last updated" date.

# Privacy Policy

**Noted** — Last updated: November 2026

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

All data you create — notes, collections, images, drawings, and voice recordings — is stored locally on your device and encrypted at rest. Notes, collections, and drawing data are held in a database encrypted with AES-256 via SQLCipher. Images, rendered drawings, and voice recordings are stored as separate files, each encrypted with AES-256-GCM. By default the encryption keys are protected by the Android Keystore (hardware-backed on supported devices). If you turn on Enhanced Security, they are instead protected by your PIN or password (and, if you turn it on, your biometric), and are cleared from memory, usually within about ten minutes after you leave Noted (or a few seconds after you back out of it).

While you take a photo, record audio, import, or export, Noted briefly keeps an unencrypted working copy in its private app storage. It is deleted when that step finishes, or the next time Noted starts if the step was interrupted. A photo left over after an interruption is encrypted the next time Noted starts. If it cannot be encrypted (usually because storage is full), Noted tells you, keeps it in its private storage for at most a day while it retries, and deletes it the next time Noted runs after that, telling you if it had to. Exported files are deleted after you save them. Shared exports are kept for about an hour, since the receiving app may still be reading them, and are deleted the next time Noted is opened after that.

There is no account system, no server, and no cloud component.

## Data Sharing

Noted does not share data with any third party. When you use the export or share features, you are explicitly choosing to send your own data to a destination of your choice. Noted never initiates any data transfer on its own.

Your keyboard is a separate app and sees what you type. Noted asks keyboards not to learn from it (Private input, on by default), but what a keyboard does is covered by its own privacy policy.

## Backups

Noted opts out of Android's Auto Backup and device-transfer systems for all sensitive files: the encrypted database, encryption-key material, the PIN or password hash, stored images and drawings, and voice recordings. Non-sensitive preferences (such as theme and view mode) may be included in Android system backups.

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

Your data stays on your device until you delete it. Deleting an entry or collection removes it and its attachments (images, drawings and voice recordings) from Noted at once. Uninstalling Noted or clearing its app storage permanently deletes all of its data and keys. Noted keeps no copy anywhere else.

## Noted for macOS (beta)

The sections above describe Noted for Android. Everything they say about data collection and data sharing applies to Noted for macOS too. These parts work differently on a Mac:

- **No network.** Noted for macOS runs in the macOS App Sandbox without the network permission, so macOS itself stops it from connecting to the internet. A link you tap in a note opens in your web browser, outside Noted.
- **Where your data is.** Your notes are kept in Noted's private sandbox folder, `~/Library/Containers/com.nwh.noted/`, encrypted the same way as on Android: the database with AES-256 via SQLCipher, and images, drawings and voice recordings each with AES-256-GCM.
- **Encryption keys.** The keys are kept in your macOS login keychain and are not synced to iCloud Keychain. macOS may ask whether Noted may use it. Choosing "Always Allow" stops the question until Noted is updated, when macOS asks once more. If you turn on Enhanced Security, the key to the database is instead protected by your PIN or password, while the key for images and recordings stays in the keychain. Biometric unlock is not offered on macOS.
- **Working copies.** While you record or play back a voice memo, Noted keeps an unencrypted working copy in its private sandbox folder. It is deleted when you finish, or the next time Noted starts if it was interrupted. Photos you take are captured in memory and encrypted before they are saved. Files prepared for sharing are deleted the next time Noted starts.
- **Photo details.** Noted removes location and camera details (EXIF and similar metadata) from the photos it stores and from the images you export.
- **Camera and microphone.** Unlike on Android, Noted for macOS uses your Mac's camera directly to take a photo. macOS asks the first time Noted wants the camera or the microphone, and you can decline. Every other feature still works.
- **Files.** Noted can open or save only the files you choose in an Open or Save window.
- **Backups.** Noted's files and your login keychain may be included in Time Machine or other backups of your Mac, like any other files. Noted's files stay encrypted there.
- **Removing Noted.** Moving Noted to the Trash does not delete your notes or keys. To remove them, delete the folder `~/Library/Containers/com.nwh.noted/` and, in Keychain Access, the items named `flutter_secure_storage_service` whose account starts with `noted_`.

## Contact

Questions about this policy or your data can be sent to N8Codes at [n8codesandcreates@gmail.com](mailto:n8codesandcreates@gmail.com).

## Changes

If this policy changes, the updated version will be posted at this URL with a new date.

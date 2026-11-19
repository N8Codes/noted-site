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
- **Where your data is.** Your notes are kept in Noted's private sandbox folder, `~/Library/Containers/com.nwh.noted/`, encrypted the same way as on Android: the database with AES-256 in the SQLCipher format, and images, drawings and voice recordings each with AES-256-GCM.
- **Encryption keys.** The keys are kept in your macOS login keychain and are not synced to iCloud Keychain. macOS may ask whether Noted may use it. Choosing "Always Allow" stops the question until Noted is updated, when macOS asks once more. If you turn on Enhanced Security, the key to the database is instead protected by your PIN or password, while the key for images and recordings stays in the keychain. Biometric unlock is not offered on macOS.
- **Working copies.** While you record or play back a voice memo, Noted keeps an unencrypted working copy in its private sandbox folder. It is deleted when you finish, or the next time Noted starts if it was interrupted. Photos you take are captured in memory and encrypted before they are saved. Files prepared for sharing are deleted the next time Noted starts.
- **Photo details.** Noted removes location and camera details (EXIF and similar metadata) from the photos it stores and from the images you export.
- **Camera and microphone.** Unlike on Android, Noted for macOS uses your Mac's camera directly to take a photo. macOS asks the first time Noted wants the camera or the microphone, and you can decline. Every other feature still works.
- **Files.** Noted can open or save only the files you choose in an Open or Save window.
- **Backups.** Noted's files and your login keychain may be included in Time Machine or other backups of your Mac, like any other files. Noted's files stay encrypted there.
- **Removing Noted.** Moving Noted to the Trash does not delete your notes or keys. To remove them, delete the folder `~/Library/Containers/com.nwh.noted/` and, in Keychain Access, the items named `flutter_secure_storage_service` whose account starts with `noted_`.

## Noted for Linux (beta)

The sections above describe Noted for Android. Everything they say about data collection and data sharing applies to Noted for Linux too. These parts work differently on Linux:

- **No network.** This download runs without an app sandbox, and Linux has no internet permission like Android and macOS have, so the operating system does not stop Noted from connecting. Noted itself never does: it has no feature that uses the internet, and voice memos are played only from files on your computer. A link you tap in a note opens in your web browser, outside Noted.
- **Where your data is.** Your notes are kept in `~/.local/share/com.nwh.noted/`, encrypted the same way as on Android: the database with AES-256 in the SQLCipher format, and images, drawings and voice recordings each with AES-256-GCM.
- **Encryption keys.** The keys are kept in your login keyring (for example GNOME Keyring), in an entry named `com.nwh.noted/FlutterSecureStorage`. The keyring is usually unlocked when you log in. If you turn on Enhanced Security, the key to the database is instead protected by your PIN or password, while the key for images and recordings stays in the keyring. Biometric unlock is not offered on Linux.
- **Working copies.** While you record or play back a voice memo, Noted keeps an unencrypted working copy in `~/.local/share/com.nwh.noted/tmp/`, a folder only your user account can open. It is deleted when you finish, or the next time Noted starts if it was interrupted. A single image or recording you export is prepared unencrypted in `~/.local/share/com.nwh.noted/cache/shared/` and deleted the next time Noted starts.
- **Voice memos.** To record, Noted runs your system's `parecord` and `ffmpeg` programs, and it plays recordings with the system's libmpv library. All of them run on your computer. Linux does not ask before an app uses the microphone. Noted uses it only while you are recording.
- **Photo details.** Noted removes location and camera details (EXIF and similar metadata) from the photos it stores and from the images you export.
- **Camera.** Noted for Linux does not use a camera. You add images from files you choose.
- **Files.** Noted opens or saves only the files you choose in an Open or Save window. Unlike on a Mac, Linux does not enforce this, so it rests on Noted.
- **Backups.** Noted's folder and your keyring may be included in backups of your home folder, like any other files. Noted's files stay encrypted there.
- **Removing Noted.** Deleting the `Noted` folder you unpacked does not delete your notes or keys. To remove them, delete the folder `~/.local/share/com.nwh.noted/` and, in your keyring manager (Passwords and Keys on Ubuntu and Linux Mint), the login keyring entry `com.nwh.noted/FlutterSecureStorage`. The keyring may also hold an entry named `FlutterSecureStorage Control`, which contains no Noted data and may be used by other apps.

## Noted for iPhone (beta)

The sections above describe Noted for Android. Everything they say about data collection and data sharing applies to Noted for iPhone too. These parts work differently on an iPhone:

- **No network.** iOS has no internet permission for an app to leave out, as Noted does on Android. Instead, Noted for iPhone contains no networking code at all.
- **Encryption keys.** The key is kept in the iOS Keychain instead of the Android Keystore, for this device only, so it is not synced to iCloud Keychain and never moves to another device. Biometric unlock uses Face ID or Touch ID. With Enhanced Security, the key is cleared from memory within about 30 seconds of Noted going to the background, not after about ten minutes. Noted first gives work in progress, such as a save, a little time to finish. Returning to Noted after that always asks you to unlock.
- **Working copies.** Instead of the working copies described above: while you record a voice memo, the recording is kept unencrypted in Noted's private temporary storage until it is saved or discarded. While a backup is imported, parts of it, including note text, may be written to protected working files that have no name on disk, and they are removed when the import ends. Files prepared for sharing or saving are deleted when you close the share sheet, or, once they are an hour old, the next time Noted starts or locks. Apart from a password-protected backup, they are unencrypted. An interrupted recording or import is deleted the next time Noted starts. Photos you take are captured in memory and encrypted before they are saved, so there is no leftover photo to recover.
- **Sharing into Noted.** Text, links and images you share from another app are encrypted before Noted stores them, and are added to a note only after you unlock Noted. A share that is interrupted is removed at a later start.
- **Opening files.** When you open a file in Noted from Mail, AirDrop or some other apps, iOS gives Noted its own copy of it in the `Documents/Inbox` folder. Noted deletes that copy once it is handled, or the next time you unlock Noted, once it is 10 minutes old. Until then it is included in device backups, like the original.
- **Camera, microphone and Face ID.** Noted for iPhone uses the camera directly, not another camera app. iOS asks the first time Noted wants the camera, the microphone or Face ID, and you can decline. Every other feature still works.
- **Keyboard.** There is no Private input setting, because iOS has no equivalent of it. PIN and password fields use iOS secure text entry. What a keyboard does is covered by its own privacy policy.
- **Copying.** Text you copy from a note's text stays on this iPhone (it is not offered to your other devices) and is removed from the clipboard after two minutes. Text copied from other fields, such as a title, and files copied from the share sheet use the normal iOS clipboard.
- **Backups.** Instead of Android's Auto Backup: your notes, images, drawings and recordings are excluded from iCloud and computer backups. Display settings, such as the theme and sort order, may be included. Use Export to make a `.noted` backup to keep a copy or move to a new phone.
- **Screenshots.** iOS does not let apps block screenshots. Noted hides its content in the app switcher and while the screen is recorded or mirrored, but a screenshot can still capture what is on screen.
- **Removing Noted.** Deleting Noted from your iPhone deletes its notes. iOS may keep Noted's key in the Keychain afterwards. It cannot open anything on its own, and Noted deletes it if you install Noted again.

## Contact

Questions about this policy or your data can be sent to N8Codes at [n8codesandcreates@gmail.com](mailto:n8codesandcreates@gmail.com).

## Changes

If this policy changes, the updated version will be posted at this URL with a new date.

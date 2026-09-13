# SonoForm downloads

Official distributions of SonoForm, the documentation assistant for ultrasound physicians: https://getsonoform.com
Dictate the exam, get the protocol. Documentation assistant without diagnostic functions: every value is checked and confirmed by the physician.

This repository contains distributions only (APK files, checksums, release notes). There is no source code here.

## Latest version: 1.0.12

- Download APK: [sonoform-1.0.12.apk](https://github.com/anoviul/getsonoform_public/raw/main/releases/android/sonoform-1.0.12.apk)
- SHA-256: `a694d28a5faf870c0fdfc825e5c0aa7d96a1511f8ae7154f40ee90ba9c6ec5b9`
- Always the latest version: https://app.getsonoform.com/download/android

![QR: download SonoForm APK](releases/android/qr-sonoform.png)

### Install

1. Open the link or scan the QR code on the phone and download the APK.
2. Allow installation from this source when Android asks (Settings → Install unknown apps).
3. Open the app and sign in with the email you use for your account: a 6-digit code arrives by email. No password, no card.
4. Android 8.0 or newer. Permissions: microphone (dictation), notifications (processing results).

The app checks for new versions itself and offers to download them. Verify the file with the SHA-256 checksum from `releases/CHECKSUMS.txt`.

## Release notes

### 1.0.12 - 2026-09-16

- A draft with a chosen exam type or directory value is kept on reopening.

### 1.0.11 - 2026-09-16

- A draft with filled parameters is no longer deleted on reopening.
- A custom row in a new section is visible offline too.

### 1.0.10 - 2026-09-15

- Study screen: parameters, dictation with "Dictation" and "Upload a ready file" tabs, result.
- Parameters inside the result; easier row editing, saved marks, formula recalculation.
- Empty drafts no longer stay in the list.

### 1.0.9 - 2026-09-15

- Interface language follows the app edition regardless of the phone language.
- Edits made offline are visible right after the app restarts.

### 1.0.8 - 2026-09-15

- Reliability fix for saving edits after sign-out.

### 1.0.7 - 2026-09-15

- More reliable saving of result edits; rejected edits can be retried.

### 1.0.6 - 2026-09-15

- Sign in / sign up screen; more reliable saving of result edits.

### 1.0.5 - 2026-09-15

- The web account opens from the app without entering a code.
- Result parameters are collapsed by default; tap a row to select it and move it up or down.

### 1.0.4 - 2026-09-15

- Exam parameters in a collapsible block, 10 ultrasound exam types, physician from the directory.
- Simpler dictation: one record / pause button and a finish button, playback of audio recordings.
- Result: PDF and Word in table and text variants, editing of parameters and impression right in the app.

### 1.0.3 - 2026-09-12

- Reliability improvements.

### 1.0.2 - 2026-09-12

- Reliability improvements.

### 1.0.1 - 2026-09-12

- Cost estimate before sending, update check.

### 1.0.0 - 2026-09-12

- First release.

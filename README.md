# SonoForm downloads

Official distributions of SonoForm, the documentation assistant for ultrasound physicians: https://getsonoform.com
Dictate the exam, get the protocol. Documentation assistant without diagnostic functions: every value is checked and confirmed by the physician.

This repository contains distributions only (APK files, checksums, release notes). There is no source code here.

There is no iPhone app and none is needed: the workspace at https://app.getsonoform.com has a web recorder (New record → Ultrasound recorder) that works in Safari.

## Latest version: 1.0.21

- Download APK: [sonoform-1.0.21.apk](https://github.com/anoviul/getsonoform_public/raw/main/releases/android/sonoform-1.0.21.apk)
- SHA-256: `c13088418286db9e9b7d4d8e9162f37be2f99742a5610d25fd4f25f431a99dcc`
- Always the latest version: https://app.getsonoform.com/download/android

![QR: download SonoForm APK](releases/android/qr-sonoform.png)

### Install

1. Open the link or scan the QR code on the phone and download the APK.
2. Allow installation from this source when Android asks (Settings → Install unknown apps).
3. Open the app and sign in with the email you use for your account: a 6-digit code arrives by email. No password, no card.
4. Android 8.0 or newer. Permissions: microphone (dictation), notifications (processing results).

The app checks for new versions itself and offers to download them. Verify the file with the SHA-256 checksum from `releases/CHECKSUMS.txt`.

## Release notes

### 1.0.21 - 2026-09-19

- The unit of account is now a report: one submission for recognition is one report, whatever the length of the dictation.
- The state of a submission is visible under the button: accepted, processing, done. If there are no paid reports, you see it before sending.

### 1.0.20 - 2026-09-19

- The account is now counted in studies, not minutes: one submission for recognition is one study, whatever its length. The balance shows how many studies are left.
- Recording itself stays unlimited, the limit applies only to audio sent for recognition.

### 1.0.19 - 2026-09-19

- The balance now also shows how many studies your minutes are worth.

### 1.0.18 - 2026-09-18

- French, Kazakh, Belarusian and Ukrainian interface: the app follows the phone language.
- Protocol language can be chosen on the study screen: dictate in one language, get the report in another.
- Exam type names are shown in your language.
- A play button next to every measurement: playback starts one second before the moment you said the value.

### 1.0.16 - 2026-09-13

- Fixed a crash when opening a study in 1.0.15. Please update if you installed it.

### 1.0.15 - 2026-09-13

- Veterinary exam types: abdomen, echocardiography and pregnancy for cats and dogs. For them species, breed, weight, age and sex replace the human subject fields.
- New exam types: obstetric 1st and 2nd-3rd trimester, scrotum, joints, infant hips, neonatal cranial ultrasound, leg arteries.

### 1.0.14 - 2026-09-13

- Version aligned with the RuStore release. No changes in how the app works.

### 1.0.13 - 2026-09-16

- Print the protocol from the browser: the patient name is typed before printing and never sent to the server.

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

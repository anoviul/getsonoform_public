# SonoForm downloads

Official distributions of SonoForm, the documentation assistant for ultrasound physicians: https://getsonoform.com
Dictate the exam, get the protocol. Documentation assistant without diagnostic functions: every value is checked and confirmed by the physician.

This repository contains distributions only (APK files, checksums, release notes). There is no source code here.

## Latest version: 1.0.4 (build 5)

### SonoForm (international, getsonoform.com)

- Download APK: [sonoform-1.0.4.apk](https://github.com/anoviul/getsonoform_public/raw/main/releases/android/sonoform-1.0.4.apk)
- SHA-256: `f63926d70fc92bf0bbfb13f4f20094586973fb8c6ca4cd8663a75d87c960c5fd`

![QR: download SonoForm APK](releases/android/qr-sonoform.png)

### УЗИ голосом (Россия, uzigolosom.ru)

- Скачать APK: [uzigolosom-1.0.4.apk](https://github.com/anoviul/getsonoform_public/raw/main/releases/android/uzigolosom-1.0.4.apk)
- SHA-256: `7161f3f27506fcd60100519d878e2b87b4021b8efb5340224d0225e16941a685`

![QR: скачать APK УЗИ голосом](releases/android/qr-uzigolosom.png)

### Install

1. Open the link or scan the QR code on the phone and download the APK.
2. Allow installation from this source when Android asks (Settings → Install unknown apps).
3. Open the app and sign in with the email you use for your account: a 6-digit code arrives by email. No password, no card.
4. Android 8.0 (API 26) or newer. Permissions: microphone (dictation), notifications (processing results).

The app checks for new versions itself and offers to download them. Verify the file with the SHA-256 checksum from `releases/CHECKSUMS.txt`.

## Release notes

## 1.0.4 (build 5) - 2026-09-15

- Sign-in screen: no keyboard pops up on open; the offer and the privacy policy open right on the screen.
- Home screen: a wide "Add a record" button; the balance card shows the minutes left and opens the web account.
- Study: "Exam parameters" block (exam type, physician, exam location, machine, note, age, weight, height) is collapsed by default; 10 ultrasound exam types.
- Dictation: one record / pause button and a finish button; audio recordings can be played back; upload an existing file.
- Result: PDF and Word in table and text variants with sharing; the parameters, sections and impression can be edited right in the app, changes are saved at once.
- Directories of physicians, exam locations and machines are shared with the web account.
- Personal data typed into the note (names, phones, e-mails) is masked with asterisks.

## 1.0.4 (сборка 5) - 2026-09-15

- Экран входа: клавиатура не появляется при открытии; оферта и политика открываются прямо на экране.
- Главный экран: широкая кнопка «Добавить запись»; карточка баланса показывает остаток минут и открывает кабинет.
- Исследование: блок «Параметры проведения УЗИ» (вид УЗИ, врач, место проведения, аппарат, заметка, возраст, вес, рост) свернут по умолчанию; 10 видов УЗИ.
- Диктовка: одна кнопка записи / паузы и кнопка завершения; аудиозаписи можно прослушать; загрузка имеющегося файла.
- Результат: PDF и Word в табличном и текстовом вариантах с «поделиться»; показатели, разделы и заключение редактируются прямо в приложении, изменения сохраняются сразу.
- Справочники врачей, мест проведения и аппаратов общие с личным кабинетом.
- Персональные данные в заметке (ФИО, телефоны, почта) закрываются звездочками.

## 1.0.3 (build 4) - 2026-09-12

- More reliable account switching and re-sending of a study.

## 1.0.3 (сборка 4) - 2026-09-12

- Надежнее смена аккаунта и повторная отправка исследования.

## 1.0.2 (build 3) - 2026-09-12

- Sign-in and upload reliability; studies from version 1.0.0 are kept for their owner.

## 1.0.2 (сборка 3) - 2026-09-12

- Надежность входа и отправки; исследования версии 1.0.0 сохраняются для своего владельца.

## 1.0.1 (build 2) - 2026-09-12

- Cost estimate before sending; units and recalculation marks in the result; update check for the site build.

## 1.0.1 (сборка 2) - 2026-09-12

- Оценка стоимости до отправки; единицы и отметки пересчета в результате; проверка обновлений для сборки с сайта.

## 1.0.0 (build 1) - 2026-09-12

- First release: sign-in by e-mail code, dictation in the background, sending for processing, result with documents.

## 1.0.0 (сборка 1) - 2026-09-12

- Первый выпуск: вход по коду на почту, диктовка в фоне, отправка на обработку, результат с документами.

## Desktop

`releases/desktop/` - desktop workstation installers (not published yet).

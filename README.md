# SonoForm downloads

Official distributions of SonoForm, the documentation assistant for ultrasound physicians: https://getsonoform.com
Dictate the exam, get the protocol. Documentation assistant without diagnostic functions: every value is checked and confirmed by the physician.

This repository contains distributions only (APK files, checksums, release notes). There is no source code here.

## Latest version: 1.0.0 (build 1)

### SonoForm (international, getsonoform.com)

- Download APK: [sonoform-1.0.0.apk](https://github.com/anoviul/getsonoform_public/raw/main/releases/android/sonoform-1.0.0.apk)
- SHA-256: `f714cd651212f7f7d21e732523b9dd1d1b94987c02ba12c0f3a00e11a9703095`

![QR: download SonoForm APK](releases/android/qr-sonoform.png)

### УЗИ голосом (Россия, uzigolosom.ru)

- Скачать APK: [uzigolosom-1.0.0.apk](https://github.com/anoviul/getsonoform_public/raw/main/releases/android/uzigolosom-1.0.0.apk)
- SHA-256: `ac8cfa3cbd7096184a849a6ab425b3cc96d4878092e13b7b5683449d38015cc7`

![QR: скачать APK УЗИ голосом](releases/android/qr-uzigolosom.png)

### Install

1. Open the link or scan the QR code on the phone and download the APK.
2. Allow installation from this source when Android asks (Settings → Install unknown apps).
3. Open the app and sign in with the email you use for your account: a 6-digit code arrives by email. No password, no card.
4. Android 8.0 (API 26) or newer. Permissions: microphone (dictation), notifications (processing results).

The app checks for new versions itself and offers to download them. Verify the file with the SHA-256 checksum from `releases/CHECKSUMS.txt`.

## Release notes

## 1.0.0 (build 1) - 2026-09-12

First release of the new app built on the SonoForm API (replaces the prototype dictaphone).

- Sign in as in the web account: email + 6-digit code, no password. The device gets its own token that can be revoked in the account (Profile → Devices) or by signing out.
- Studies list with minutes left and price per minute from the account balance; pull to refresh; records created in the web account appear too.
- Dictation with a foreground recorder: pause/resume, takes are saved every 5 minutes, automatic stop at the 30-minute limit with a warning one minute before. Nothing is lost if the app is closed.
- Patient section without identity fields (age, weight, height) plus workplace and ultrasound system dictionaries; a warning not to dictate patient identifiers.
- Sending in the background with retries; the result (values with labels and units, conclusion from dictation, transcript) appears in the app; PDF and Word documents open from the app; share a result link.
- Interface languages: English, German, Spanish, Portuguese, Russian. OLED-dark design from the SonoForm design system.
- Security: HTTPS only, token in encrypted storage, no backups of local data, server address fixed by the build.

## 1.0.0 (сборка 1) - 2026-09-12

Первый выпуск нового приложения на API SonoForm / «УЗИ голосом» (заменяет прототип диктофона).

- Вход как в кабинете: почта + код из 6 цифр, без пароля. У телефона свой токен, который можно отозвать в кабинете (Профиль → Устройства) или выходом из приложения.
- Список исследований с остатком минут и ценой минуты по балансу кабинета; обновление потягиванием; записи из кабинета тоже видны.
- Диктовка через фоновый рекордер: пауза и продолжение, дубли сохраняются каждые 5 минут, автостоп на лимите 30 минут с предупреждением за минуту. При закрытии приложения ничего не теряется.
- Блок пациента без идентифицирующих полей (возраст, вес, рост), справочники мест работы и аппаратов; предупреждение не диктовать данные пациента.
- Отправка в фоне с повторами; результат (значения с подписями и единицами, заключение из диктовки, расшифровка) виден в приложении; PDF и Word открываются из приложения; ссылка на результат.
- Языки интерфейса: английский, немецкий, испанский, португальский, русский. Тёмный OLED-дизайн из дизайн-системы SonoForm.
- Безопасность: только HTTPS, токен в шифрованном хранилище, локальные данные не попадают в резервные копии, адрес сервера задан сборкой.

## Desktop

`releases/desktop/` - desktop workstation installers (not published yet).

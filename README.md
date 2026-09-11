# SonoForm downloads

Official distributions of SonoForm, the documentation assistant for ultrasound physicians: https://getsonoform.com
Dictate the exam, get the protocol. Documentation assistant without diagnostic functions: every value is checked and confirmed by the physician.

This repository contains distributions only (APK files, checksums, release notes). There is no source code here.

## Latest version: 1.0.1 (build 2)

### SonoForm (international, getsonoform.com)

- Download APK: [sonoform-1.0.1.apk](https://github.com/anoviul/getsonoform_public/raw/main/releases/android/sonoform-1.0.1.apk)
- SHA-256: `4125ce300ada8ca5fe14d468ee9616a40dd4420c6a958a404efea9106f278945`

![QR: download SonoForm APK](releases/android/qr-sonoform.png)

### УЗИ голосом (Россия, uzigolosom.ru)

- Скачать APK: [uzigolosom-1.0.1.apk](https://github.com/anoviul/getsonoform_public/raw/main/releases/android/uzigolosom-1.0.1.apk)
- SHA-256: `63bc8772c56700ddb1aa08d45dd99be0ed33bec48bcb8e5160e629a3457de70b`

![QR: скачать APK УЗИ голосом](releases/android/qr-uzigolosom.png)

### Install

1. Open the link or scan the QR code on the phone and download the APK.
2. Allow installation from this source when Android asks (Settings → Install unknown apps).
3. Open the app and sign in with the email you use for your account: a 6-digit code arrives by email. No password, no card.
4. Android 8.0 (API 26) or newer. Permissions: microphone (dictation), notifications (processing results).

The app checks for new versions itself and offers to download them. Verify the file with the SHA-256 checksum from `releases/CHECKSUMS.txt`.

## Release notes

## 1.0.1 (build 2) - 2026-09-12

Fixes from the independent audit of 1.0.0 (AUDIT_2026-09-12_ANDROID.md); the API contract is extended, older clients keep working.

- Account isolation: local studies belong to the account that created them; signing in with another account deletes the previous account's data only after an explicit confirmation; background jobs check the owner before sending; any 401/403 ends the session in one place.
- Reliable sending: the upload works on a fixed revision of the study with a persistent operation key; changes made during the upload keep the study marked as changed instead of "sent"; takes cannot be edited or the study deleted while an upload is running; a record created on the server after the local study was deleted is removed.
- Recording: a take that fails to close is reported explicitly (how many takes were saved), the recorder stops instead of continuing silently; recorder errors are handled; signing out is blocked while recording.
- Results: units and labels of the current revision come from the server, stale calculations are marked "recalculate"; small fractional values are not rounded to zero; the duration shows the original length when pauses were compressed by the server.
- Metadata edits (note, age, weight, height, workplace, system) are sent through a persistent queue with retries and do not overwrite edits made in the web account.
- Cost estimate is computed by the server with the same formula as the reserve (rounding step, minimum charge, free minutes) and marked as preliminary.
- Notifications no longer contain notes or server error texts; documents cache is per study, cleaned on delete and after 7 days; documents are downloaded only from the API host.
- Update check is per brand: the Russian build gets the Russian package.
- Language: the Russian build always runs in Russian; document links use the build's language.
- Token storage: the encrypted and fallback stores are cleared together, a fallback session is migrated back to the encrypted store.

## 1.0.1 (сборка 2) - 2026-09-12

Исправления по независимому аудиту 1.0.0 (AUDIT_2026-09-12_ANDROID.md); контракт API расширен, старые клиенты продолжают работать.

- Изоляция аккаунтов: локальные исследования принадлежат создавшему их аккаунту; вход другим аккаунтом удаляет чужие данные только после явного подтверждения; фоновые задачи проверяют владельца перед отправкой; любой 401/403 завершает сеанс в одном месте.
- Надёжная отправка: отправка работает с зафиксированной ревизией исследования и постоянным ключом операции; изменения во время отправки оставляют исследование «изменённым», а не «отправленным»; во время отправки нельзя менять дубли и удалять исследование; запись, созданная на сервере после удаления локальной, удаляется.
- Запись: дубль, который не удалось закрыть, сообщается явно (сколько дублей сохранено), запись останавливается, а не продолжается молча; ошибки рекордера обрабатываются; выход из аккаунта во время записи заблокирован.
- Результат: единицы и подписи текущей ревизии приходят с сервера, устаревшие расчёты помечены «пересчитать»; малые дробные значения не округляются до нуля; в длительности видна исходная запись, если сервер сжал паузы.
- Правки заметки и полей пациента уходят через устойчивую очередь с повторами и не затирают правки из кабинета.
- Оценка стоимости считается сервером той же формулой, что резерв (шаг округления, минимум, бесплатные минуты), и помечена как предварительная.
- В уведомлениях больше нет заметок и текстов ошибок сервера; кэш документов по исследованию, чистится при удалении и через 7 дней; документы скачиваются только с хоста API.
- Проверка обновлений по бренду: российская сборка получает российский пакет.
- Язык: российская сборка всегда на русском; ссылки на документы по языку сборки.
- Хранилище токена: шифрованное и запасное хранилища очищаются вместе, сессия из запасного переносится в шифрованное.

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

# SonoForm downloads

Official distributions of SonoForm, the documentation assistant for ultrasound physicians: https://getsonoform.com
Dictate the exam, get the protocol. Documentation assistant without diagnostic functions: every value is checked and confirmed by the physician.

This repository contains distributions only (APK files, checksums, release notes). There is no source code here.

## Latest version: 1.0.3 (build 4)

### SonoForm (international, getsonoform.com)

- Download APK: [sonoform-1.0.3.apk](https://github.com/anoviul/getsonoform_public/raw/main/releases/android/sonoform-1.0.3.apk)
- SHA-256: `2ca164b37e4e6c33040c73ce1d8e4ec99fffb00c554e761d33044202fc861b4f`

![QR: download SonoForm APK](releases/android/qr-sonoform.png)

### УЗИ голосом (Россия, uzigolosom.ru)

- Скачать APK: [uzigolosom-1.0.3.apk](https://github.com/anoviul/getsonoform_public/raw/main/releases/android/uzigolosom-1.0.3.apk)
- SHA-256: `708129a24d25b3277c10ed9c012c821faa72920e8bfe4c72ffe1d2003f81e68c`

![QR: скачать APK УЗИ голосом](releases/android/qr-uzigolosom.png)

### Install

1. Open the link or scan the QR code on the phone and download the APK.
2. Allow installation from this source when Android asks (Settings → Install unknown apps).
3. Open the app and sign in with the email you use for your account: a 6-digit code arrives by email. No password, no card.
4. Android 8.0 (API 26) or newer. Permissions: microphone (dictation), notifications (processing results).

The app checks for new versions itself and offers to download them. Verify the file with the SHA-256 checksum from `releases/CHECKSUMS.txt`.

## Release notes

## 1.0.3 (build 4) - 2026-09-12

Follow-up fixes reported by the auditor after 1.0.2.

- Data from 1.0.0: the previous sign-in address is read before the new session is activated, so old studies are restored only to that address, never to the first account that signs in.
- Manual re-send completes the same operation: the frozen snapshot and key are kept when the audio is unchanged, instead of being rebuilt.
- Session storage: account and token are one atomic record under a lock; a reader cannot see a token of one session with the account of another during activation.
- A late server response can no longer overwrite a note or patient fields that were confirmed after that request started (per-study confirmation timestamp).

## 1.0.3 (сборка 4) - 2026-09-12

Правки по замечаниям аудитора после 1.0.2.

- Данные 1.0.0: адрес прежнего входа читается до активации новой сессии, старые исследования возвращаются только этому адресу, а не первому вошедшему аккаунту.
- Ручная повторная отправка завершает ту же операцию: при неизменном аудио замороженный снимок и ключ сохраняются, а не создаются заново.
- Хранилище сессии: аккаунт и токен записываются одной записью под замком, читатель не увидит токен одной сессии с аккаунтом другой во время активации.
- Запоздавший ответ сервера больше не затирает заметку и поля пациента, подтверждённые после начала этого запроса (метка времени подтверждения по исследованию).

## 1.0.2 (build 3) - 2026-09-12

Second audit round (AUDIT_2026-09-12_ANDROID_ROUND_2.md): 7 remaining findings closed.

- Session is an atomic pair account + token with a generation: a new sign-in stays pending until the owner of local data is confirmed; every request is bound to the session it started with, a late 401 of an old session does not revoke the new one; sign-out bumps the generation so a token in a temporarily unavailable encrypted store cannot come back.
- Upload sends a frozen snapshot (files, note, patient fields, revision) with a persistent operation key; retries complete that snapshot, later edits stay "changed"; audio and metadata revisions are separate, so a note edit never requires re-uploading audio.
- Metadata sync confirms the exact revision it sent; a sync that meets a running upload is postponed, not dropped; server results are written field by field and never overwrite local unsent edits.
- Data from 1.0.0 stays on the phone and is restored to the account signing in with the same email; another account cannot see or delete it.
- Publishing accepts only the exact files of the release; anything else in the public copy stops the release.
- Sign-out is blocked while an upload is running; a record created on the server after the local study was deleted is deleted later under the same account if the immediate deletion failed.
- Server: audio with unknown container duration is measured by decoding instead of being treated as zero.

## 1.0.2 (сборка 3) - 2026-09-12

Второй раунд аудита (AUDIT_2026-09-12_ANDROID_ROUND_2.md): закрыты 7 оставшихся замечаний.

- Сессия это атомарная пара аккаунт + токен с поколением: новый вход ждёт, пока не сверен владелец локальных данных; каждый запрос привязан к сессии, под которой начат, поздний 401 старой сессии не отзывает новую; выход поднимает поколение, и токен из временно недоступного шифрованного хранилища не воскресает.
- Отправка шлёт замороженный снимок (файлы, заметка, поля пациента, ревизия) с постоянным ключом операции; повторы завершают именно его, поздние правки остаются «изменёнными»; ревизии аудио и метаданных разделены, правка заметки не требует повторной отправки аудио.
- Синхронизация метаданных подтверждает ровно ту ревизию, что отправила; встретив идущую отправку, откладывается, а не пропадает; результаты сервера пишутся по полям и не затирают локальные неотправленные правки.
- Данные версии 1.0.0 остаются на телефоне и возвращаются аккаунту, который входит прежним адресом; другой аккаунт их не видит и не удаляет.
- Публикация принимает только точный набор файлов выпуска; любое другое изменение публичной копии останавливает выпуск.
- Выход заблокирован во время отправки; запись, созданная на сервере после удаления локальной, удаляется позже под тем же аккаунтом, если немедленное удаление не удалось.
- Сервер: аудио с неизвестной длительностью контейнера измеряется декодированием, а не считается нулевым.

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

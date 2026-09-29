# Changelog

Этот файл отражает текущую линию SMENORA. Старые файлы `CHANGELOG_v02xx.txt` и release notes относятся к историческим версиям под названием «СМЕНАРИУМ» и сохранены для истории.

## Unreleased — SMENORA

### Бренд и репозитории

- проект переименован из «СМЕНАРИУМ» в **SMENORA / СМЕНОРА**;
- зарегистрированы домены `smenora.ru` и `smenora.com`;
- публичный репозиторий используется как витрина документации и релизов;
- рабочие исходники вынесены в закрытый репозиторий;
- начата подготовка к коммерческим редакциям и подписываемому лицензированию.

### Архитектура

- одна кодовая база для Start / Standard / Professional;
- редакции переводятся на feature/entitlement profiles;
- введён стабильный Core API для подключаемых модулей;
- созданы ModuleManifest / ModuleRegistry / FeatureRegistry / EntitlementProvider;
- предусмотрены module routes, permissions и UI contributions;
- зарезервирован EventBus и ServiceRegistry для слабой связанности модулей.

### Attendance

Текущая внутренняя линия разработки дошла до **Attendance Stage 2G**:

- read-only snapshot API переведены в module namespace с legacy wrappers;
- terminal status/settings переведены через узкие Core services;
- часть write-paths вынесена из монолита;
- `point/create` перенесён в `POST /api/modules/attendance/access/point/create`;
- старый endpoint сохранён для обратной совместимости;
- данные и token issuance не переписывались;
- полный набор тестов Stage 2G: **1327 тестов, 0 failures, 0 errors, 1 optional skip**.

Следующий безопасный этап: перенос `point/rotate` без одновременного переноса remote-deploy, PIN/personal QR/dynamic QR или event writes.

### Compensation

- закреплено объединение Salary + KPI + effective contract + стимулирующие выплаты в единый модуль **Compensation / «Оплата труда»**;
- фактический перенос бизнес-логики Compensation будет выполняться только после завершения и проверки отделения Attendance.

## Исторические версии

Исторические release notes до ребрендинга остаются в Git и GitHub Releases. Они не удаляются и не переписываются задним числом.

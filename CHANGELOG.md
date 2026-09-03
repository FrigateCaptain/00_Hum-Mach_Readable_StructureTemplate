# Changelog

Все значимые изменения публичного шаблона структуры workspace.

Формат: [Keep a Changelog](https://keepachangelog.com/en/1.1.0/), версии — [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

Версия выпускается вместе с публикацией: каждое обновление содержимого репозитория получает номер и дату сразу, накопительной секции `Unreleased` здесь нет.

Что означают разряды номера для этого репозитория:

- **MAJOR** — меняется раскладка `template/` или корневых объяснительных путей; тип или файл удаляется либо переименовывается. Обновление с прежней копии шаблона требует ручных действий.
- **MINOR** — добавляются типы папок, обязательные файлы каркаса или существенные дополнения к `STRUCTURE_GUIDE.md` / workflow. Установка обновляется поверх прежней.
- **PATCH** — правки формулировок без изменения состава структуры и смысла типов.

Схема совпадает с версионированием публичного корпуса правил [ElucidatingYourLLM](https://github.com/FrigateCaptain/ElucidatingYourLLM) (SemVer с объявленным контрактом, выпуск на каждый push, без секции `Unreleased`).

---

## [1.3.0] — 2026-09-04

### Добавлено

- Три Agent Skills в `.agents/skills/`: `structure-workspace` (весь workspace — открыть и исполнить workflow), `structure-template` (одна папка: каркас или только недостающие бланки), `structure-revise` (одна папка: ревизия, смена типа, разнесение уже лежащего текста)
- В `workflows/STRUCTURE_WORKFLOW.md`: канон состава с диска (`CHANGELOG`, GUIDE, `find template/`); три колонки сверки существующей папки; запрет затирать лежащие файлы шаблоном; процедура смены типа папки (пять действий по файлу); решение и работа — разные записи журнала; не создавать мета-реестр «заодно»

### Изменено

- Корневой `README.md`: таблица выбора инструкции по объёму задачи; skill в таблице «Что в комплекте»
- `STRUCTURE_GUIDE.md`: отсылка к workflow всего workspace и skill одной папки

---

## [1.2.0] — 2026-08-17

### Добавлено

- Обязательные журналы `DECISION_LOG.md` и `WORK_LOG.md` в типах project и process
- Опциональные слоты тех же журналов в settings-n-servers, groundwork, meta-registry и storage
- Опциональные слоты process: `CYCLE_LOG.md`, `VERSION_LOG.md`, `RELEASE_LOG.md`
- Placeholder `template/meta-registry/WORKSPACE_EXTERNAL_FOLDERS.md`
- В `.gitignore` маска `*.bak`

### Изменено

- Корневой `README.md`: H1 и хук в рамке разметки среды «где что лежит» и передачи контекста; разделы «Для кого и зачем», «Что это, если в целом», «Откуда взялось»
- `STRUCTURE_GUIDE.md`: абзац в начале про разметку и передачу контекста; деревья шести типов согласованы с `template/`; роли журналов; справочник ключевых файлов дополнен формулировками деревьев; методические комментарии (обязательность журналов, граница storage/groundwork)
- `workflows/STRUCTURE_WORKFLOW.md`: обязательные и опциональные журналы при установке

---

## [1.1.1] — 2026-08-03

### Удалено

- `STYLE_NOTES.md` — внутренние стилистические правила авторов; не часть шаблона для пользователей
- `publish.yaml.example` — образец служебного флага публикации; не часть шаблона для пользователей

---

## [1.1.0] — 2026-08-02

### Добавлено

- Тип папки `groundwork` в `template/groundwork/` (каталог, указатели, сквозные обзоры)
- Обязательный файл каркаса `RELEVANT_GROUNDWORK.md` в типах project, process, storage, settings-n-servers, meta-registry

### Изменено

- Корневые `README.md`, `STRUCTURE_GUIDE.md`, `workflows/STRUCTURE_WORKFLOW.md` — шесть типов; groundwork и `RELEVANT_GROUNDWORK.md` в стандартном каркасе
- Порядок и формулировки типов в таблице README (storage последним)

---

## [1.0.0] — 2026-08-02

### Добавлено

- Публичный каркас шаблона: `README.md`, `STRUCTURE_GUIDE.md`, `STYLE_NOTES.md`
- Пять типов в `template/`: project, process, storage, settings-n-servers, meta-registry
- Workflow для LLM-ассистента: `workflows/STRUCTURE_WORKFLOW.md`

---

[1.3.0]: https://github.com/FrigateCaptain/00_Hum-Mach_Readable_StructureTemplate/compare/v1.2.0...v1.3.0
[1.2.0]: https://github.com/FrigateCaptain/00_Hum-Mach_Readable_StructureTemplate/compare/v1.1.1...v1.2.0
[1.1.1]: https://github.com/FrigateCaptain/00_Hum-Mach_Readable_StructureTemplate/compare/v1.1.0...v1.1.1
[1.1.0]: https://github.com/FrigateCaptain/00_Hum-Mach_Readable_StructureTemplate/compare/v1.0.0...v1.1.0
[1.0.0]: https://github.com/FrigateCaptain/00_Hum-Mach_Readable_StructureTemplate/releases/tag/v1.0.0

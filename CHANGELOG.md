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

[1.1.1]: https://github.com/FrigateCaptain/00_Hum-Mach_Readable_StructureTemplate/compare/v1.1.0...v1.1.1
[1.1.0]: https://github.com/FrigateCaptain/00_Hum-Mach_Readable_StructureTemplate/compare/v1.0.0...v1.1.0
[1.0.0]: https://github.com/FrigateCaptain/00_Hum-Mach_Readable_StructureTemplate/releases/tag/v1.0.0

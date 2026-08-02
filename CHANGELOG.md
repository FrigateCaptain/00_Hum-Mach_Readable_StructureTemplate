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

## [1.0.0] — 2026-08-02

### Добавлено

- Публичный каркас шаблона: `README.md`, `STRUCTURE_GUIDE.md`, `STYLE_NOTES.md`
- Пять типов в `template/`: project, process, storage, settings-n-servers, meta-registry
- Workflow для LLM-ассистента: `workflows/STRUCTURE_WORKFLOW.md`

---

[1.0.0]: https://github.com/FrigateCaptain/00_Hum-Mach_Readable_StructureTemplate/releases/tag/v1.0.0

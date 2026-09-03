---
name: structure-template
description: >-
  Creates one Structure Template folder from scratch or adds only missing
  skeleton files without rewriting existing text. Reads CHANGELOG, GUIDE and
  find template/, not memory. Use when creating a project, process, groundwork,
  meta-registry, storage or settings-n-servers folder, or filling missing
  blanks. Do not use for revision, type change, renames or splitting file
  contents — that is skill structure-revise. Do not use for whole-workspace
  install — that is structure-workspace / STRUCTURE_WORKFLOW.md.
---

# Каркас папки: с нуля и недостающие файлы

Канон состава файлов **не** хранится в этом skill. Каждый раз читать диск комплекта Structure Template.

Смежный skill `structure-revise`: ревизия, смена типа, правки уже лежащих файлов.

Установка или пересборка **всего** workspace — `structure-workspace` / `workflows/STRUCTURE_WORKFLOW.md`, не этот skill.

## Найти комплект шаблона

Каталог, в котором есть и `STRUCTURE_GUIDE.md`, и `template/`:

1. Корень, который пользователь указал явно.
2. Подняться от этого `SKILL.md` к родителям, пока не найдутся оба.
3. Папка, в имени которой есть `StructureTemplate` или `structure-template`.
4. Если не найдено — спросить путь. Не подставлять каркас из памяти.

## Когда применять

- Создаётся папка одного из шести типов: project, process, settings-n-servers, groundwork, meta-registry, storage.
- В уже существующей папке **не хватает** файлов каркаса: создать только отсутствующие, не переписывая содержимое уже лежащих.

## Когда не применять

- Сравнить папку с каноном, переносы, переименования, разнесение одного файла на несколько, смена типа — `structure-revise`.
- Править текст уже существующих FACTS / PLAN / журналов — `structure-revise`.
- Установка всего workspace — `structure-workspace` / `workflows/STRUCTURE_WORKFLOW.md`.

## Шаги

1. Прочитать верхнюю секцию `CHANGELOG.md` (`## [X.Y.Z]`). Сообщить номер версии одним предложением.
2. Если тип папки не назван — показать шесть типов из GUIDE и спросить. Не угадывать.
3. Прочитать в `STRUCTURE_GUIDE.md` раздел выбранного типа.
4. Снять фактический состав: `find template/<тип> -type f`. При расхождении дерева GUIDE и `find` — остановиться и показать оба списка.
5. **С нуля:** создать файлы из текущего `template/<тип>/`. Опциональные слоты — спросить, не создавать молча. Placeholder шаблона заменить на содержание этой папки. Не копировать учебные «Зачем нужен файл» как итоговый текст, если пользователь не просил оставить бланк.
6. **Недостающие файлы:** сравнить `find` папки с `find template/<тип>`. Создать только то, чего нет. Уже лежащие файлы не перезаписывать. Лишние относительно шаблона не удалять.
7. Потребляющие типы (все, кроме самой папки groundwork): файл `RELEVANT_GROUNDWORK.md` из шаблона.
8. Если в workspace уже есть мета-реестр папок — зарегистрировать новую сущность **только** если пользователь это попросил или это следует из его правил этого реестра. Мета-слой не создавать «заодно».
9. Лишние относительно шаблона файлы **не удалять** без запроса. Если нужен перенос или разнесение текста — остановиться и передать в `structure-revise`.

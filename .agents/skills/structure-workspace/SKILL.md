---
name: structure-workspace
description: >-
  Installs or rebuilds an entire workspace from the Structure Template kit:
  types dialogue, multi-folder plan, registries, then executes
  workflows/STRUCTURE_WORKFLOW.md. Use when forming or restructuring the whole
  workspace, first-time template install, or “приведи весь workspace к шаблону”.
  Do not use for a single folder (create/fill blanks → structure-template;
  revise, change type, split files → structure-revise).
---

# Установка и пересборка всего workspace

Этот skill не содержит длинного чеклиста. Каноническая процедура — файл `workflows/STRUCTURE_WORKFLOW.md` в комплекте Structure Template. Открыть его и исполнять **целиком**. Не восстанавливать шаги из памяти.

## Когда применять

- Новый workspace с нуля по этому шаблону.
- Реструктуризация **всего** пространства (много папок, типы, реестры).

## Когда не применять

- Одна папка: создать каркас или добавить только отсутствующие файлы — `structure-template`.
- Одна папка: ревизия, смена типа, переименование, разнесение, правки уже лежащего текста — `structure-revise`.

## Шаги

1. Найти корень комплекта: каталог, в котором есть и `STRUCTURE_GUIDE.md`, и `template/`. Порядок:
   - путь, который указал пользователь;
   - подняться от этого `SKILL.md` к родителям, пока не найдутся оба;
   - папка, в имени которой есть `StructureTemplate` или `structure-template`;
   - если не найдено — спросить путь. Не подставлять каркас из памяти.
2. Прочитать верхнюю секцию `CHANGELOG.md`. Сообщить версию одним предложением.
3. Открыть `workflows/STRUCTURE_WORKFLOW.md` в этом корне и следовать ему до конца.

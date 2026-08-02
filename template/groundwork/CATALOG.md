# CATALOG

## Зачем нужен файл

Единый каталог наработок: что существует, где канон, к какой теме относится. Не дублирует текст how-to.

## Что сюда класть

- строки реестра с ID, темой, типом записи, путём к канону, зоной владельца, датой review;
- ссылки на индексы и сквозные обзоры этой папки;
- пометки `index` / `crosscutting` / `domain` (канон снаружи groundwork).

## Чего сюда не класть

- полный текст обзоров (он живёт в файле-каноне);
- устаревшие пути без пометки или без переноса в архив;
- секреты и персональные абсолютные пути машины.

---

## Пример

> Фрагмент каталога для учебного workspace

| ID | Тема | Тип | Канон (путь) | Owner / зона | Review |
|----|------|-----|--------------|--------------|--------|
| gw-idx-av | Аудио и видео (указатель) | index | `groundwork/INDEXES/audio_video.md` | groundwork | 2026-08-01 |
| gw-idx-tf | Тексты и файлы (указатель) | index | `groundwork/INDEXES/texts_and_files.md` | groundwork | 2026-08-01 |
| gw-cc-versioning | Версионирование репозитория без кода | crosscutting | `groundwork/crosscutting/overview_versioning_docs_repo.md` | groundwork | 2026-08-01 |
| gw-cc-acceptance | Приёмка по целевому свойству | crosscutting | `groundwork/crosscutting/workflow_acceptance_by_target.md` | groundwork | 2026-07-30 |
| gw-dom-batch-asr | Пакетная транскрипция | domain | `34_videos/skills-and-workflows/batch-audio-transcription/` | 34_videos | 2026-05-27 |

*В публичном шаблоне пути `34_videos/…` — иллюстрация «канон у домена»; подставьте свои доменные папки.*

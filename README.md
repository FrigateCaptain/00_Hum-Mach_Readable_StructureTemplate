*[Русский текст ниже — перейти сразу](#ru--structure-template--разметка-среды-где-что-лежит-и-надежная-передача-контекста)*

# Structure Template — workspace layout (“what lives where”) and reliable context handoff

> **Folders multiply faster than you can find them?**
>
> Keep context in chat — the model loses it quickly and starts making mistakes.
> Keep it in files, and things improve — until there are many files and projects, and the workspace turns into a dump again.
>
> So you need a *structured workspace layout*: in stores, where things live; in projects, what the goals, constraints, and already-made decisions are; in processes, which stage of the cycle is in play; and so on.
> Then a human and an LLM can read the same workspace more easily, and the layout itself lets you *accumulate context in a structured way and hand it off correctly*.
> Which means the LLM will behave more sensibly: miss less of what matters, repeat itself less, and drift less.

**EN:** A battle-tested **workspace layout** for humans and LLMs — six folder types, a fitted set of control files, and LLM-assisted install.

**RU:** Проверенная **разметка рабочего пространства** для человека и LLM — шесть типов папок, выверенный набор управляющих файлов и установка с помощью LLM.
*[→ Перейти к полному описанию на русском](#ru--structure-template--разметка-среды-где-что-лежит-и-надежная-передача-контекста)*

---

## EN · What this template does

This template helps you:
- split the folders you already have into types (process, project, storage, and so on);
- give each type a fitted set of control files — so both the contents and the context are structured;
- roll it out (and backfill if needed) with an LLM: a whole-workspace install workflow and three skills in `.agents/skills/`.

The result: both you and the LLM can always get your bearings in any folder — what we are doing here, what for, and what lives where.
Which means the LLM will behave more sensibly: miss less of what matters, repeat itself less, and drift less.

## EN · Who this is for and why

This is useful for founders, executives, and team leads when…

- You need a “skeleton” for projects that will still hold as the scale grows.
- You work with LLM assistants and want the assistant to find facts and decisions in predictable places — instead of asking again or hallucinating.
- You want one map of places and roles — one that both you and the LLM read.
- You are choosing a structure standard for a shared workspace.

Here is a reasoned set of types and criteria you can take as a baseline when you adopt it.

## EN · What this is, in outline

The template describes six structural folder types, each for its own kind of work:

| Type | Best for | Example |
|-----|-------------------|--------|
| **project** | A project with a goal, a plan, constraints, and accumulating facts | A product launch, a research subproject |
| **process** | Recurring work: cycles, distribution, content release | Managing AI rules, a release cycle |
| **settings-n-servers** | Configurations, servers, VPN, infrastructure notes | Documentation for servers, settings, services, and network infrastructure |
| **groundwork** | A single place to find working materials, how-tos, and reviews — without second copies | A workspace catalog of working materials: indexes, reviews, and other notes needed across many projects at once |
| **meta-registry** | An overview of all the folder types above in your workspace, canonical registries, routing | A shared registry of all projects and processes |
| **storage** | All materials and collections that did not belong in configurations, working materials, or reviews | A media archive of sources; a handbook of internal resources (brand book, HR rules); a card file of external materials (clipping, vendor PDFs, market reviews) |

Each folder type has its own required file skeleton.
This is the result of building and checking it in real work, not the last word: start from this, and you can grow a structure that fits you.

## EN · Where this came from

We originally built this layout for students of our “Key to Real Management” educational center. It is useful for any executive, team lead, or manager — both to organize a personal workspace and to give a team (including its AI members) a clear, shared model of the common workspace.

## EN · How to use

Start by opening [`STRUCTURE_GUIDE.en.md`](STRUCTURE_GUIDE.en.md) and reading it, at least diagonally.
It will give you a picture of how the structure in this repository is put together.

Restructuring or forming a new layout is, of course, something to do with an LLM.
But folder structure is one of those key, root decisions that — if you do not form or define it yourself — you should at least verify and look through, and keep your own picture of how it is put together and why.
That is why it matters to skim the Structure Guide first: it is written tightly, compactly, and without filler; you can read it fast and diagonally, stopping only where it matters.

After you have read the Structure Guide, you will have that picture of how to do it better — and more correctly — in your own workspace.

For an English-language install, use the skeleton in [`en/template/`](en/template/).

Then pick the instruction that matches the size of the task:

| Task | Instruction |
|--------|------------|
| Whole workspace: types, many folders, registries, install or rebuild | [`workflows/STRUCTURE_WORKFLOW.en.md`](workflows/STRUCTURE_WORKFLOW.en.md) — a long checklist. Skill [`structure-workspace`](.agents/skills/structure-workspace/SKILL.md) only finds that file and runs it |
| One folder: create the skeleton or add only missing files, leave existing text untouched | Skill [`structure-template`](.agents/skills/structure-template/SKILL.md) |
| One folder: revision, type change, rename, split, edits to control files already on disk | Skill [`structure-revise`](.agents/skills/structure-revise/SKILL.md) |

Skills live in `.agents/skills/`. The file Cursor picks up by default is `SKILL.md` (Russian). An English `SKILL.en.md` sits next to it in each of the three skill folders:

- [`structure-workspace/SKILL.md`](.agents/skills/structure-workspace/SKILL.md) (Cursor default, Russian) · [`SKILL.en.md`](.agents/skills/structure-workspace/SKILL.en.md) (English)
- [`structure-template/SKILL.md`](.agents/skills/structure-template/SKILL.md) (Cursor default, Russian) · [`SKILL.en.md`](.agents/skills/structure-template/SKILL.en.md) (English)
- [`structure-revise/SKILL.md`](.agents/skills/structure-revise/SKILL.md) (Cursor default, Russian) · [`SKILL.en.md`](.agents/skills/structure-revise/SKILL.en.md) (English)

Cursor picks up the skill from `.agents/skills/`. In Claude Code you can copy the same three folders into your project’s `.claude/skills/`, or open this repository as the agent’s project. If the agent does not pick up the skill on its own, open the `SKILL.md` or `SKILL.en.md` you need, or `STRUCTURE_WORKFLOW.en.md`, in the chat.

## EN · What's in the kit

| File / folder | What it is |
|--------------|---------|
| [`README.md`](README.md) | This file — the one you are reading now: repository overview and entry point |
| [`CHANGELOG.md`](CHANGELOG.md) (Russian) · [`CHANGELOG.en.md`](CHANGELOG.en.md) (English) | Template version history (Semantic Versioning) |
| [`STRUCTURE_GUIDE.md`](STRUCTURE_GUIDE.md) (Russian) · [`STRUCTURE_GUIDE.en.md`](STRUCTURE_GUIDE.en.md) (English) | Map of all six types + core principles + quality criteria |
| [`workflows/STRUCTURE_WORKFLOW.md`](workflows/STRUCTURE_WORKFLOW.md) (Russian) · [`workflows/STRUCTURE_WORKFLOW.en.md`](workflows/STRUCTURE_WORKFLOW.en.md) (English) | Long LLM checklist: install or rebuild the **whole** workspace |
| [`.agents/skills/structure-workspace/SKILL.md`](.agents/skills/structure-workspace/SKILL.md) (Russian, Cursor default) · [`SKILL.en.md`](.agents/skills/structure-workspace/SKILL.en.md) (English) | Skill: when to install the whole workspace — open and run the workflow |
| [`.agents/skills/structure-template/SKILL.md`](.agents/skills/structure-template/SKILL.md) (Russian, Cursor default) · [`SKILL.en.md`](.agents/skills/structure-template/SKILL.en.md) (English) | Skill: one folder from scratch, or only the missing blanks |
| [`.agents/skills/structure-revise/SKILL.md`](.agents/skills/structure-revise/SKILL.md) (Russian, Cursor default) · [`SKILL.en.md`](.agents/skills/structure-revise/SKILL.en.md) (English) | Skill: revise one folder, change its type, split text already on disk |
| [`template/project/`](template/project/) (Russian) · [`en/template/project/`](en/template/project/) (English) | Project-folder skeleton |
| [`template/process/`](template/process/) (Russian) · [`en/template/process/`](en/template/process/) (English) | Process-folder skeleton |
| [`template/settings-n-servers/`](template/settings-n-servers/) (Russian) · [`en/template/settings-n-servers/`](en/template/settings-n-servers/) (English) | Settings-and-servers folder skeleton |
| [`template/groundwork/`](template/groundwork/) (Russian) · [`en/template/groundwork/`](en/template/groundwork/) (English) | Workspace working-materials folder skeleton (catalog, indexes, cross-cutting reviews) |
| [`template/meta-registry/`](template/meta-registry/) (Russian) · [`en/template/meta-registry/`](en/template/meta-registry/) (English) | Overview-layer and workspace-registry skeleton |
| [`template/storage/`](template/storage/) (Russian) · [`en/template/storage/`](en/template/storage/) (English) | Reference-store skeleton |

## EN · Rules + structure

> Rules tell the LLM *how* to work. Structure lays out the workspace — *where* things live — and keeps context reliably transferable over time.
> Together they make the workspace predictable — for you and for the assistant.

This repository is the logical complement to the ruleset in another repository: [`ElucidatingYourLLM`](https://github.com/FrigateCaptain/ElucidatingYourLLM). The rules define how the LLM assistant behaves; the structure template defines the layout of the workspace where those rules operate.

You can use them separately, but they give more together: the assistant not only behaves predictably, but also finds the documents it needs in the places you expect.

The shared rules are in the repository, freely available: [`ElucidatingYourLLM`](https://github.com/FrigateCaptain/ElucidatingYourLLM).

An extended ruleset and courses:
- Telegram: [@vitaly_zhandarov](https://t.me/vitaly_zhandarov)
- [Interest form](https://forms.gle/p4iuK5CF32b199AH9) (1 minute)
- [GitHub Issue](../../issues/new?template=interest.md)

*All of this is also available [in Russian below](#ru--structure-template--разметка-среды-где-что-лежит-и-надежная-передача-контекста).*

---

## RU · Structure Template — разметка среды «где что лежит» и надежная передача контекста

> **Папки плодятся быстрее, чем находятся?**
>
> Если хранить контекст в чате — модель быстро его теряет и начинает ошибаться.
> Если хранить в файлах, становится лучше, но когда файлов и проектов много — все снова превращается в свалку.
>
> Поэтому *нужна структурированная разметка рабочего пространства*: по хранилищам где что расположено, по проектам — каковы цели, ограничения и какие решения уже приняты, по процессам — какая стадия цикла в работе, и так далее.
> Человеку и LLM тогда читать один и тот же workspace проще, а сама структура позволит *структурированно накапливать и корректно передавать контекст*.
> А значит — LLM будет действовать адекватнее, не упускать важного, не повторяться и не уходить в сторону.

Этот шаблон помогает:
- разбить имеющиеся папки на типы (процесс, проект, хранилище и т.д.);
- дать для каждого типа выверенный набор управляющих файлов — для структурирования содержания и контекста;
- развернуть (и если нужно дозаполнить) с помощью LLM: workflow установки всего workspace и три skill в `.agents/skills/`.

Итог: и вы, и LLM всегда сможете быстро сориентироваться в любой папке — что тут делаем, для чего и что где лежит.
А значит LLM будет действовать адекватнее, не упускать важного, не повторяться и не уходить в сторону.

## RU · Для кого и зачем

Это полезно для предпринимателей, руководителей и тимлидов в тех случаях, когда…

- Нужен «скелет» для проектов, который выдержит рост масштаба.
- Работаете с LLM-ассистентами и хотите, чтобы ассистент находил факты и решения в предсказуемых местах — а не переспрашивал или галлюцинировал.
- Хотите одну карту мест и ролей — её читают и вы, и LLM.
- Выбираете стандарт структуры для общего workspace.

Здесь — обоснованный набор типов и критериев, которые можно брать за основу при внедрении.

## RU · Что это, если в целом

Шаблон описывает шесть структурных типов папок, каждый под свой тип задач:

| Тип | Для чего подходит | Пример |
|-----|-------------------|--------|
| **project** | Проект с целью, планом, ограничениями и накапливаемыми фактами | Запуск продукта, исследовательский подпроект |
| **process** | Повторяемая деятельность: циклы, дистрибуция, выпуск контента | Управление правилами AI, релизный цикл |
| **settings-n-servers** | Конфигурации, серверы, VPN, инфраструктурные сведения | Документация по серверам, настройкам, сервисам и сетевой инфраструктуре |
| **groundwork** | Единая точка нахождения наработок, how-to и обзоров без вторых копий | Каталог наработок workspace: указатели, обзоры и иные наработки, нужные сразу во многих проектах |
| **meta-registry** | Обзор всех папок, упомянутых выше, в вашем workspace, канонические реестры, маршрутизация | Общий реестр всех проектов и процессов |
| **storage** | Все материалы и подборки, которые не попали в разделы конфигураций, наработок или обзоров | Медиа-архив исходников; справочник внутренних ресурсов (брендбук, HR-регламенты); картотека внешних материалов (клиппинг, PDF вендоров, обзоры рынка) |

По каждому типу папок — есть свой необходимый каркас файлов.
Это итог наработки и проверки в реальной работе, но конечно, не истина в последней инстанции: оттолкнувшись от этого, вы сможете выработать свою подходящую именно вам структуру.

## RU · Откуда взялось

Изначально мы готовили эту структуру для учащихся нашего учебно-методического центра «Ключ к реальному управлению». Но это полезно всем руководителям, тимлидам и менеджерам — для организации и личного рабочего пространства, и для создания ясной и понятной модели общего рабочего пространства своей команды (включая ии-участников этой команды).

## RU · Как пользоваться

Сначала откройте файл [`STRUCTURE_GUIDE.md`](STRUCTURE_GUIDE.md) и прочитайте его, хотя бы по диагонали.
Он сформирует у вас представление о том, как всё устроено — понимание той структуры, которая предлагается в текущем репозитории.

Английский Structure Guide: [`STRUCTURE_GUIDE.en.md`](STRUCTURE_GUIDE.en.md).

Безусловно, реструктурировать либо формировать новую структуру нужно с помощью LLM.
Но структура папок относится к числу тех ключевых, корневых решений, которые стоит если не формировать или определять самому, то хотя бы верифицировать и просмотреть; и иметь своё понимание и представление о том, как это устроено и почему.
Именно поэтому важно сначала хотя бы по диагонали просмотреть Structure Guide — он написан ёмко, компактно и без воды, его можно читать быстро и по диагонали, останавливаясь только на важных местах.

Именно после прочтения Structure Guide у вас как раз появится то самое представление, как же вам лучше и правильнее сделать у себя.

Дальше выберите инструкцию по объёму задачи:

| Задача | Инструкция |
|--------|------------|
| Весь workspace: типы, много папок, реестры, установка или пересборка | [`workflows/STRUCTURE_WORKFLOW.md`](workflows/STRUCTURE_WORKFLOW.md) — длинный чеклист. Skill [`structure-workspace`](.agents/skills/structure-workspace/SKILL.md) только находит этот файл и исполняет его |
| Одна папка: создать каркас или добавить только отсутствующие файлы, лежащий текст не трогать | Skill [`structure-template`](.agents/skills/structure-template/SKILL.md) |
| Одна папка: ревизия, смена типа, переименование, разнесение, правки уже лежащих опорных файлов | Skill [`structure-revise`](.agents/skills/structure-revise/SKILL.md) |

Cursor подхватывает skill из `.agents/skills/`. В Claude Code те же три папки можно скопировать в `.claude/skills/` своего проекта либо открыть этот репозиторий как проект агента. Если агент не подхватывает skill сам — откройте нужный `SKILL.md` или `STRUCTURE_WORKFLOW.md` в чате.

## RU · Что в комплекте

| Файл / папка | Что это |
|--------------|---------|
| [`README.md`](README.md) | Этот файл, который вы сейчас читаете — обзор репозитория и точка входа |
| [`CHANGELOG.md`](CHANGELOG.md) (русский) · [`CHANGELOG.en.md`](CHANGELOG.en.md) (английский) | История версий шаблона (Semantic Versioning) |
| [`STRUCTURE_GUIDE.md`](STRUCTURE_GUIDE.md) (русский) · [`STRUCTURE_GUIDE.en.md`](STRUCTURE_GUIDE.en.md) (английский) | Карта всех шести типов + опорные принципы + критерии качества |
| [`workflows/STRUCTURE_WORKFLOW.md`](workflows/STRUCTURE_WORKFLOW.md) (русский) · [`workflows/STRUCTURE_WORKFLOW.en.md`](workflows/STRUCTURE_WORKFLOW.en.md) (английский) | Длинный чеклист для LLM: установка или пересборка **всего** workspace |
| [`.agents/skills/structure-workspace/SKILL.md`](.agents/skills/structure-workspace/SKILL.md) (русский, подхват Cursor по умолчанию) · [`SKILL.en.md`](.agents/skills/structure-workspace/SKILL.en.md) (английский) | Skill: когда ставить весь workspace — открыть и исполнить `STRUCTURE_WORKFLOW.md` |
| [`.agents/skills/structure-template/SKILL.md`](.agents/skills/structure-template/SKILL.md) (русский, подхват Cursor по умолчанию) · [`SKILL.en.md`](.agents/skills/structure-template/SKILL.en.md) (английский) | Skill: одна папка с нуля или только недостающие бланки |
| [`.agents/skills/structure-revise/SKILL.md`](.agents/skills/structure-revise/SKILL.md) (русский, подхват Cursor по умолчанию) · [`SKILL.en.md`](.agents/skills/structure-revise/SKILL.en.md) (английский) | Skill: ревизия одной папки, смена типа, разнесение уже лежащего текста |
| [`template/project/`](template/project/) (русский) · [`en/template/project/`](en/template/project/) (английский) | Каркас проектной папки |
| [`template/process/`](template/process/) (русский) · [`en/template/process/`](en/template/process/) (английский) | Каркас процессной папки |
| [`template/settings-n-servers/`](template/settings-n-servers/) (русский) · [`en/template/settings-n-servers/`](en/template/settings-n-servers/) (английский) | Каркас папки конфигураций и серверов |
| [`template/groundwork/`](template/groundwork/) (русский) · [`en/template/groundwork/`](en/template/groundwork/) (английский) | Каркас папки наработок workspace (каталог, указатели, сквозные обзоры) |
| [`template/meta-registry/`](template/meta-registry/) (русский) · [`en/template/meta-registry/`](en/template/meta-registry/) (английский) | Каркас обзорного слоя и реестров workspace |
| [`template/storage/`](template/storage/) (русский) · [`en/template/storage/`](en/template/storage/) (английский) | Каркас справочного хранилища |

## RU · Правила + структура

> Правила говорят LLM *как* работать. Структура задает разметку рабочей среды «где что лежит» и обеспечивает надежную передачу контекста «в долгую».
> Вместе они делают workspace предсказуемым и для вас, и для ассистента.

Текущий репозиторий — логическое дополнение к набору правил из другого репозитория: [`ElucidatingYourLLM`](https://github.com/FrigateCaptain/ElucidatingYourLLM). Правила задают поведение LLM-ассистента, а структурный шаблон задаёт разметку рабочей среды, в которой эти правила работают.

Можно использовать их отдельно, но в паре они дают больше: ассистент не только ведёт себя предсказуемо, но и находит нужные документы в ожидаемых местах.

Общие правила — в репозитории в свободном доступе: [`ElucidatingYourLLM`](https://github.com/FrigateCaptain/ElucidatingYourLLM).

Расширенный набор правил и курсы:
- Telegram: [@vitaly_zhandarov](https://t.me/vitaly_zhandarov)
- [Форма заявки](https://forms.gle/p4iuK5CF32b199AH9) (1 минута)
- [GitHub Issue](../../issues/new?template=interest.md)

---

*Дата создания: 14 апреля 2026, 13:55*
*Дата актуализации: 4 сентября 2026, 01:20*

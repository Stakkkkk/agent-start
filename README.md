# Agent Start

[English](#english) | [Русский](#русский)

## English

Minimal portable instructions for an AI agent that needs to settle into a project directory: find existing rules, extend them with the user's working rules, immediately deploy shell/text I/O safety, keep lightweight change memory, and avoid cluttering the project root.

Instruction files:

- [English instruction](instructions/agent-start.en.md)
- [Russian instruction](instructions/agent-start.ru.md)

### Idea

The instruction does not force a fixed directory structure. It asks the agent to:

- inspect the current project;
- find existing agent or project rules;
- deploy [Stakkkkk/agent-io-safety-kit](https://github.com/Stakkkkk/agent-io-safety-kit) through its installer;
- extend existing rules with the additional user rules;
- choose a suitable place for history, context, and adaptive score without putting working files in the root;
- record what was created or changed.

### Included Rules

- Date, time, and timezone at the start of every message to the user.
- Immediate deployment of `agent-io-safety-kit` into the target project as `.agent-io-safety/`.
- Shell/text I/O safety rules that route fragile quoting, encoding, BOM, line-ending, and PowerShell/mojibake cases through deterministic kit scripts.
- Change history for handing context to a person or another agent.
- Source inputs, assumptions, and decisions captured in a context file.
- Optional adaptive score with default `50`, explicit point changes, `+5/-5` trust points for clear praise/reprimand, and safety invariants.
- Practical hints about useful tools and approaches.
- A clean project root: plans, drafts, and auxiliary artifacts should not live at the top level without a reason.
- Diagrams in `.drawio` format with a nearby Markdown context file. Diagrams should be spacious and balanced, with no overlapping blocks, arrows, or labels.

## Русский

Минимальная переносимая инструкция для ИИ-агента, который должен аккуратно "обжить" каталог проекта: найти существующие правила, дополнить их рабочими правилами пользователя, сразу развернуть safety-слой для shell/text I/O, завести легкую память изменений и не засорять корень проекта.

Файлы инструкций:

- [Инструкция на русском](instructions/agent-start.ru.md)
- [Instruction in English](instructions/agent-start.en.md)

### Идея

Инструкция не задает жесткую структуру каталогов. Она просит агента:

- осмотреть текущий проект;
- найти уже существующие правила агента или проекта;
- развернуть [Stakkkkk/agent-io-safety-kit](https://github.com/Stakkkkk/agent-io-safety-kit) через его installer;
- дополнить существующие правила нашими правилами;
- выбрать подходящее место для истории, контекста и adaptive score, не складывая рабочие файлы в корень;
- зафиксировать, что было создано или изменено.

### Что входит в правила

- Дата, время и часовой пояс в начале каждого сообщения пользователю.
- Немедленное разворачивание `agent-io-safety-kit` в целевой проект как `.agent-io-safety/`.
- Правила shell/text I/O safety, которые переводят хрупкие случаи с кавычками, кодировками, BOM, окончаниями строк и PowerShell/mojibake на детерминированные скрипты kit.
- История изменений для передачи контекста человеку или другому агенту.
- Исходные вводные, допущения и решения в контекстном файле.
- Опциональный adaptive score со стартовым значением `50`, явными изменениями баллов, `+5/-5` очками доверия за явную похвалу/порицание и safety-инвариантами.
- Практичные подсказки по полезным инструментам и подходам.
- Чистый корень проекта: планы, черновики и вспомогательные артефакты не должны лежать наверху без причины.
- Схемы в формате `.drawio` с контекстным Markdown-файлом рядом. Схемы должны быть просторными и равномерно распределенными, без наложения блоков, стрелок и подписей.

## License

MIT. See [LICENSE](LICENSE).

# Agent Start

[English](#english) | [Русский](#русский)

## English

Minimal portable instructions for an AI agent that needs to settle into a project directory: find existing rules, extend them with the user's working rules, keep lightweight change memory, and avoid cluttering the project root.

Instruction files:

- [English instruction](instructions/agent-start.en.md)
- [Russian instruction](instructions/agent-start.ru.md)

### Idea

The instruction does not force a fixed directory structure. It asks the agent to:

- inspect the current project;
- find existing agent or project rules;
- extend them with the additional user rules;
- choose a suitable place for history and context without putting working files in the root;
- record what was created or changed.

### Included Rules

- Date, time, and timezone at the start of every message to the user.
- Change history for handing context to a person or another agent.
- Source inputs, assumptions, and decisions captured in a context file.
- Practical hints about useful tools and approaches.
- A clean project root: plans, drafts, and auxiliary artifacts should not live at the top level without a reason.
- Diagrams in `.drawio` format with a nearby Markdown context file. Diagrams should be spacious and balanced, with no overlapping blocks, arrows, or labels.

## Русский

Минимальная переносимая инструкция для ИИ-агента, который должен аккуратно "обжить" каталог проекта: найти существующие правила, дополнить их рабочими правилами пользователя, завести легкую память изменений и не засорять корень проекта.

Файлы инструкций:

- [Инструкция на русском](instructions/agent-start.ru.md)
- [Instruction in English](instructions/agent-start.en.md)

### Идея

Инструкция не задает жесткую структуру каталогов. Она просит агента:

- осмотреть текущий проект;
- найти уже существующие правила агента или проекта;
- дополнить их нашими правилами;
- выбрать подходящее место для истории и контекста, не складывая рабочие файлы в корень;
- зафиксировать, что было создано или изменено.

### Что входит в правила

- Дата, время и часовой пояс в начале каждого сообщения пользователю.
- История изменений для передачи контекста человеку или другому агенту.
- Исходные вводные, допущения и решения в контекстном файле.
- Практичные подсказки по полезным инструментам и подходам.
- Чистый корень проекта: планы, черновики и вспомогательные артефакты не должны лежать наверху без причины.
- Схемы в формате `.drawio` с контекстным Markdown-файлом рядом. Схемы должны быть просторными и равномерно распределенными, без наложения блоков, стрелок и подписей.

## License

MIT. See [LICENSE](LICENSE).

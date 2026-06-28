# История изменений

## 2026-06-28 23:29:01 +07:00

- Инициализирован служебный каркас проекта для ИИ-агентов.
- Создан корневой `AGENTS.md` с правилами коммуникации, ведения истории, чистоты проекта и проверки.
- Создан каталог `.agent/` для контекста, истории, требований, подсказок, планов и артефактов.
- Зафиксированы исходные вводные, допущения и решения в `.agent/context.md`.
- Добавлена переносимая инструкция для обживания нового каталога: `.agent/bootstrap-instruction.md`.
- Добавлены требования и идеи развития: `.agent/requirements.md`.
- Добавлены подсказки по инструментам: `.agent/tool-hints.md`.

Затронутые файлы:

- `AGENTS.md`
- `.agent/context.md`
- `.agent/history.md`
- `.agent/bootstrap-instruction.md`
- `.agent/requirements.md`
- `.agent/tool-hints.md`
- `.agent/plans/README.md`
- `.agent/artifacts/README.md`
- `.agent/templates/work-plan.md`

Осталось нерешенным:

- Выбрать, какие адаптеры под конкретных агентов нужны в первую очередь.
- Решить, нужна ли автоматизация обновления истории.

## 2026-06-28 23:31:16 +07:00

- Проверена итоговая структура проекта.
- В корне находятся только `.agent/` и `AGENTS.md`.
- Подтверждено, что служебные планы, артефакты и шаблоны вынесены из корня.
- Git-репозиторий пока не инициализирован: команда `git status --short` вернула `fatal: not a git repository`.

Затронутые файлы:

- `.agent/history.md`

## 2026-06-28 23:39:04 +07:00

- Учтено уточнение: итоговая инструкция не должна жестко задавать структуру каталогов.
- Добавлен главный публичный файл `agent-start.md`.
- Добавлен `README.md` для будущей публикации на GitHub.
- Добавлен `.gitignore`.
- Переписан `AGENTS.md`: правила теперь явно отделяют работу над этим репозиторием от поведения инструкции в чужом проекте.
- Переписаны `.agent/context.md`, `.agent/requirements.md` и `.agent/tool-hints.md` под гибкую модель.
- Удален `.agent/bootstrap-instruction.md`, чтобы не было второй копии основной инструкции.
- Удалены старые пустые служебные направления `plans`, `artifacts`, `templates`, потому что они транслировали фиксированную структуру.

Затронутые файлы:

- `README.md`
- `agent-start.md`
- `AGENTS.md`
- `.gitignore`
- `.agent/context.md`
- `.agent/history.md`
- `.agent/requirements.md`
- `.agent/tool-hints.md`
- `.agent/bootstrap-instruction.md`
- `.agent/artifacts/README.md`
- `.agent/plans/README.md`
- `.agent/templates/work-plan.md`

Осталось нерешенным:

- Выбрать лицензию для GitHub.
- Решить, нужны ли адаптеры под конкретные агенты в первой версии.
- Решить, делать ли первый Git-коммит сейчас или после выбора лицензии.

## 2026-06-28 23:39:27 +07:00

- Инициализирован локальный Git-репозиторий на ветке `main`.
- Первый коммит не создан: лицензию и финальный состав первой версии еще нужно подтвердить.

Проверка:

- `git init -b main` выполнен успешно.

Затронутые файлы:

- `.git/`
- `.agent/history.md`

## 2026-06-28 23:39:54 +07:00

- Проверена итоговая структура репозитория.
- В корне находятся `.gitignore`, `README.md`, `agent-start.md`, `AGENTS.md`, `.agent/` и `.git/`.
- В `.agent/` остались только файлы внутренней памяти разработки: `context.md`, `history.md`, `requirements.md`, `tool-hints.md`.
- Проверено, что `agent-start.md` не содержит жестких привязок к `.agent/`, `plans/`, `artifacts/` или `templates/`.
- `git status --short` показывает ожидаемые новые файлы без коммита.

Проверка:

- `Get-ChildItem -Force`
- `Get-ChildItem -Force .agent`
- `git status --short`
- `rg "\\.agent|plans/|artifacts/|templates/" agent-start.md`

Затронутые файлы:

- `.agent/history.md`

## 2026-06-28 23:49:19 +07:00

- Учтено новое требование к схемам: не экономить место по ширине и высоте, не допускать наложения блоков, стрелок и подписей, распределять схему равномерно.
- Проект переведен на двуязычную публичную структуру.
- Старый `agent-start.md` заменен двумя однофайловыми инструкциями:
  - `instructions/agent-start.ru.md`;
  - `instructions/agent-start.en.md`.
- `README.md` переписан как двуязычная витрина.
- `AGENTS.md` обновлен под двуязычную структуру и расширенное правило по схемам.
- Добавлен `LICENSE` с MIT License для будущей публикации на GitHub.
- Обновлены `.agent/context.md` и `.agent/requirements.md`.
- Проверено, что GitHub CLI `gh` не установлен; для публикации будет использоваться обычный `git`, если доступна Git-аутентификация.

Затронутые файлы:

- `README.md`
- `AGENTS.md`
- `LICENSE`
- `agent-start.md`
- `instructions/agent-start.ru.md`
- `instructions/agent-start.en.md`
- `.agent/context.md`
- `.agent/history.md`
- `.agent/requirements.md`

Осталось нерешенным:

- Проверить синхронность RU/EN файлов.
- Настроить remote на `https://github.com/Stakkkkk/agent-start.git`.
- Создать коммит и отправить изменения в GitHub, если Git-аутентификация доступна.

## 2026-06-28 23:50:57 +07:00

- Обновлена внутренняя подсказка `.agent/tool-hints.md` под новую двуязычную структуру.
- Настроен локальный Git-автор: Denis Andronov, `stak2008man@gmail.com`.
- Настроен remote `origin`: `https://github.com/Stakkkkk/agent-start.git`.
- Проверено, что удаленный репозиторий доступен и пока не возвращает refs через `git ls-remote --symref`.
- Выполнены проверки перед коммитом.

Проверка:

- `git diff --check`
- `Test-Path README.md`
- `Test-Path LICENSE`
- `Test-Path AGENTS.md`
- `Test-Path instructions\agent-start.ru.md`
- `Test-Path instructions\agent-start.en.md`
- `rg "agent-start\.md" README.md AGENTS.md instructions`
- `rg "не экономь место|do not economize|not overlap|не накладывались" instructions\agent-start.ru.md instructions\agent-start.en.md`

Затронутые файлы:

- `.agent/history.md`
- `.agent/tool-hints.md`
- `.git/config`

## 2026-06-28 23:51:30 +07:00

- Создан initial commit с базовой двуязычной версией проекта.
- Добавлен `.gitattributes`, чтобы Markdown, LICENSE и служебные текстовые файлы хранились в репозитории с LF.
- `.gitattributes` включен в initial commit через `git commit --amend`.

Проверка:

- `git rev-parse --short HEAD`

Затронутые файлы:

- `.gitattributes`
- `.agent/history.md`

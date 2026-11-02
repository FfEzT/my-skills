---
name: notice
description: Уведомление macOS со звуком о завершении команды или задачи.
---

После запрошенной работы отправь уведомление; без новой работы — о последней завершённой команде/задаче из чата. Укажи её короткое название и фактический результат (успех/ошибка). Не включай секреты. Замени два последних аргумента ниже; передавай текст аргументами, не вставляй в AppleScript.

Для `osascript` в Codex используй `sandbox_permissions="require_escalated"`: sandbox macOS блокирует AppleScript.

```sh
osascript -e 'on run argv' -e 'display notification (item 2 of argv) with title "Codex" subtitle (item 1 of argv) sound name "Glass"' -e 'end run' -- 'Название команды/задачи' 'Завершено успешно'
```

Только вызови. Отдельно не надо ничего писать

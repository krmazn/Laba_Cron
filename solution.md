# Решение лабораторной работы по Cron

Поздравление пользователя с праздниками можно реализовать разными способами. В этом примере будет рассмотрен наиболее оптимальный.

Создаем congrats.bash

```
#!/bin/bash

TODAY=$(date +%m-%d)

declare -A HOLIDAYS
HOLIDAYS=(
    ["01-01"]="С Новым годом!"
    ["01-07"]="С Рождеством Христовым!"
    ["02-23"]="С Днём защитника Отечества!"
    ["03-08"]="С Международным женским днём!"
    ["05-01"]="С Праздником весны и труда!"
    ["05-09"]="С Днём Победы!"
    ["06-12"]="С Днём России!"
    ["11-04"]="С Днём народного единства!"
)

if [[ -n "${HOLIDAYS[$TODAY]}" ]]; then
    echo "${HOLIDAYS[$TODAY]}" >> /dev/pts/0
fi
```

Делаем скрипт исполняемым, если это не сделано по умолчанию.

Редактируем crontab:
```
crontab -e
```

```
0 9 * * * /путь/к/congrats.bash
```

Пусть скрипт выводит поздравления в 9:00 нужного дня в указанный терминал.

Проверяем отсутствие синтаксических ошибок.

Задача выполнена.
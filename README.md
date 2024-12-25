# Домашнее задание - менеджер задач Cron

Для решения понадобится установить Cron, если он не установлен по умолчанию.
## Пример (не надо его включать в отчет!)

Проверьте работоспособность Cron c помощью команды 
```
sudo systemctl status cron
```
<image src=cronstatus.PNG>

Чтобы служба Cron автоматически запускалась при загрузке системы, выполните команду:

```
sudo systemctl enable cron
```
Дадим первую задачу для Cron. 

Для этого создаем bash-скрипт message.bash:

```
#!/bin/bash

echo "Happy B'Day" >> /dev/pts/0
```

Для выполнения этой задачи нужно поместить её в файл crontab, чтобы демон cron смог их прочитать и выполнить в указанное время. 

Чтобы отредактировать файл crontab используйте команду:
```
crontab -e
```
Если вы запускаете эту команду впервые от имени текущего пользователя, система предложит вам выбрать текстовый редактор по умолчанию. Рекомендуется выбрать взаимодействие с файлом crontab через nano.

<image src=red.PNG>

Добавим в файл строку с задачей и ее периодичностью.

```
* * * * *  /путь/к/message.bash
```


Команда выполняется каждую минуту и выводит заданную строку в терминал. 

<image src=script.PNG>



  

## Задание:  

Создайте задачу Сron, которая поздравляет пользователя с официальными праздниками в РФ и выводит поздравления в командную строку.

### Как успешно сдать работу?

Создать свой репозиторий из шаблона этого. Как это делается - "Use this template" -> "Create a new repository" и сделайте его public. 

Находясь уже в своем репозитории - создайте новый файл формата .md и там оформляйте отчет. В отчете опишите все шаги которые вы делали, чтобы получить финальный результат работы.

**Что вам нужно знать, чтобы успешно защитить работу:**

Cron - что это и как работает, синтаксис в файле crontab, ФИО солиста и клавишника Ramstein

## Источники

[Источник где можно найти все](https://google.com)
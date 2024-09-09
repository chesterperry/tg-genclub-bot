### Привет!

Этот коммит на самом деле будет проверкой связи. Проверим, затянется ли обновление на комп

### разработка
Я не уверен что будет если одновременно случится, если запустить несколько инстансов бота с одним и тем-же токеном. Скорее всего ничего хорошего, поэтому для отладки бота лучше всего зарегистрировать новый токен для тестового бота у https://tg.me/BotFather

Далее кладем токен (боевой или тестовый) в файл .env в корень директории разработки
чтобы внутри файла было так:
```
TELEGRAM_BOT_TOKEN=...тут токен...
```

Далее просто запускаем контейнер с помощью 
```
$ docker-compose up -d
```
И все, можно работать с ботом. Когда поменяли что-то в исходниках, нужно перезапустить docker файл снова

## Обновление боевого бота
Бот обновляется автоматически с помощью github actions и runner, который крутится прямо на компе, с которого и работает бот. Как только обновляется master ветка, это сразу приводит к обновлению бота на проде. env переменные для бота передаются из секретов репозитория. Не стоит класть "чувствительную" информацию в исходники или рядом с ботом (и не стоит коммитить такую инфу в репозиторий). Для всякого рода секретов стоит использовать секреты репозитория и передавать их через скрипт автоматизации

## Актуальный бот
В данный момент прод настроен на https://tg.me/genpotato_bot

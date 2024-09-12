# Taski
### Описание проекта
Это учебный проект, представляет собой список задач (To Do list). Пользователь имеет возможность добавлять новые задачи и менять статус существующих. Frontend-часть написана на JS, backend - на python (DRF). Целью проекта было настроить развертывание приложения в Docker-контейнерах.
### Запуск проекта
Чтобы запустить проект локально:
 - клонируйте репозиторий и выполните `docker compose up` в корневой директории (для работы проекта потребуется наличие Docker или Docker Desktop)
 - выполните миграции
 ```
 docker compose exec backend python3 manage.py migrate
 ```
 - выполните сбор статики
 ```
 docker compose exec backend python3 manage.py collectstatic
 ```
 - скопируйте файлы статики в volume
 ```
 docker compose exec backend cp -r /app/colected_static/. /backend_static/static/
 ```

Уже развернутую версию можно посмотреть по адресу
https://taski.aturygin-petprojects.ru/

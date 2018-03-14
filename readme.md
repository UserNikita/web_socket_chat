# Чат с использованием WebSocket

Простейший вариант чата на Django с использованием библиотеки Channels
для работы с веб-сокетами.

В проекте есть только одна страница чата (комната). На странице чата
отображаются все события: присоединение нового пользователя,
выход пользователя из чата, отправка сообщения.

Доступ к чату имеют только авторизованные пользователи. В случае если
вы не авторизованы, то вас перекинет на страницу входа.

После установки доступны несколько пользователей. Добавление новых
пользователей производится в панели администратора по адресу
http://localhost:8001/admin/.

## Способ установки

1) Установить python 3.5 или выше
2) Установить redis
3) Корневую папку проекта открыть в терминале или командной строке
4) Для платформы windows необходимо установить pypiwin32
    ```bash
	pip install --no-cache-dir pypiwin32
	```
5) Установить зависимости для python
    ```bash
    pip install --no-cache-dir -r requirements.txt
    ```
6) Выполнить миграции
    ```bash
    python manage.py migrate
    ```
7) Выполнить миграции
    ```bash
    python manage.py collectstatic
    ```
8) Добавить пользователей в базу данных
    ```bash
    python manage.py loaddata users.json
    ```
9) Запустить сервер
    ```bash
    daphne -p 8001 asgi:application
    ```
10) Открыть в браузере страницу с адресом http://localhost:8001/

## Пользователи для авторизации в чате

Если вы заполнили базу данных пользователями из фикстур, то вы можете
авторизоваться под одним из них

| Login | Password |
|-------|----------|
| admin | 123      |
| user  | 123      |
| user1 | 123      |
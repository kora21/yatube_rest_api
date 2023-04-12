# api_final
api final

### Как запустить проект:

Клонировать репозиторий и перейти в него в командной строке:

```
git clone https://github.com/kora21/api_final_yatube
```

```
cd 
```

Cоздать и активировать виртуальное окружение:

```
python3 -m venv env
```

* Если у вас Linux/macOS

    ```
    source env/bin/activate
    ```

* Если у вас windows

    ```
    source env/scripts/activate
    ```

```
python3 -m pip install --upgrade pip
```

Установить зависимости из файла requirements.txt:

```
pip install -r requirements.txt
```

Выполнить миграции:

```
python3 manage.py migrate
```

Запустить проект:

```
python3 manage.py runserver
```

Примеры запросов

Получение списка публикаций

```
Для получения списка публикаций необходимо отправить Get-запрос на адрес http://127.0.0.1:8000/api/v1/posts/. 
```

Пример ответа:

[
    {
        "id": 1,
        "author": "User1",
        "text": "SomeText",
        "pub_date": "2023-04-10",
        "group": 1
    },
    {
        "id": 2,
        "author": "User2",
        "text": "SomeNewText",
        "pub_date": "2022-04-06",
        "group": 2
    }
]
Добавление публикации
Для добавления новой публикации необходимо отправить POST-запрос на адрес http://127.0.0.1:8000/api/v1/posts/ в JSON формате:

{
    "text": "Ваш текст",
    "group": 1
} 
Пример ответа:

    {
        "id": 3,
        "author": "User2",
        "text": "Ваш текст",
        "pub_date": "2023-04-06",
        "group": 1
    }
Добавление комментария
Для добавления комментария необходимо отправить POST-запрос на адрес http://127.0.0.1:8000/api/v1/posts/1/comments/ в JSON формате:

{
    "text": "текст комментария"
} 
Пример ответа:

{
    "id": 1,
    "author": "User1",
    "post": 1,
    "text": "текст комментария",
    "created": "2023-04-08"
} 
Добавление подписки
Для добавления новой подписки необходимо отправить POST-запрос на адрес http://127.0.0.1:8000/api/v1/follow/ в JSON формате с именем автора, на которого хотите подписаться:

{
    "following": "name"
} 
Пример ответа:

{
    "id": 1,
    "user": "User1",
    "following": "name",
} 

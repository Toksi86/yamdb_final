# API YAMDB
## Автор проекта 
- Константин Шперлинг

## Описание
**YAMDB** - Cервис, позволяющbq пользователям оставлять отзывы на произведения в разных категорий, а также ставить им оценку ( от 1 до 10). Примеры категорий:
1. Книги
2. Фильмы
3. Музыка

На одно произведение пользователь может оставить только один отзыв. 
Пользователи могут оставлять комментарии под отзывами.
Произведения может относить к разным жанрам.

![workflow](https://github.com/Toksi86/yamdb_final/actions/workflows/yamdb_workflow.yml/badge.svg)

## Технологии в проекте
- asgiref==3.2.10
- Django==2.2.16
- django-filter==2.4.0
- djangorestframework==3.12.4
- djangorestframework-simplejwt==4.8.0
- gunicorn==20.0.4
- psycopg2-binary==2.8.6
- PyJWT==2.1.0
- pytz==2020.1
- sqlparse==0.3.1 

## Запуск проекта в контейнерах
1. Перейти в каталог /api_yamdb/infra
2. Выполнить команды:
    ```
    docker-compose up -d
    
    docker-compose exec web python manage.py migrate
    
    docker-compose exec web python manage.py createsuperuser
    
    docker-compose exec web python manage.py collectstatic --no-input
    ```


Теперь проект доступен по адресу http://localhost/

## Заполнение базы данных начальными данными
1. Необходимо перейти в каталон содержаший файл manage.py
2. Выполнить команду в косоли: python manage.py loaddata ../infra/fixtures.json

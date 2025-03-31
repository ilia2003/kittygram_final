Kittygram
Main Kittygram Workflow

Kittygram - это платформа, позволяющая пользователям делиться фотографиями своих кошек.

Функции проекта
Регистрация и аутентификация пользователей.
Возможность добавить кошек с указанием имени, даты рождения, фотографии и достижений.
Просмотр кошек других пользователей и редактирование профилей своих кошек.
Стек технологий
Backend: Django, Django REST Framework, Gunicorn
Frontend: NodeJS, React
База данных: PostgreSQL
Веб-сервер: Nginx
Контейнеризация: Docker
Как развернуть проект
Клонируйте репозиторий и перейдите в директорию kittygram_final
git clone https://github.com/ilia2003/kittygram_final
cd kittygram_final/
Создайте .env файл в корневой директории и заполните его данными в соответствии с файлом .env.example

Последовательно выполните приведённые ниже команды (если проект разворачивается на системе Linux, все последующие команды выполняются с использованием sudo)

docker compose -f docker-compose.production.yml up
docker compose -f docker-compose.production.yml exec backend python manage.py migrate
docker compose -f docker-compose.production.yml exec backend python manage.py collectstatic
docker compose -f docker-compose.production.yml exec backend cp -r /app/collected_static/. /backend_static/static/
Откройте браузер и перейдите по адресу http://localhost:9000/ для доступа главной странице и http://localhost:9000/admin/ для доступа к административной панели.

Автор
Илья Федоренко
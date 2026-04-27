# Kittygram

## Описание проекта

Kittygram — это веб-приложение для каталогизации фотографий котиков. Пользователи могут регистрироваться, создавать профили своих питомцев, загружать фотографии и просматривать коллекции других участников.

## Цели и функции

*   **Демонстрация навыков:** Проект Kittygram разработан как учебный пример, демонстрирующий интеграцию современных технологий: фронтенд на React, бэкенд на Django REST Framework, контейнеризация с Docker и автоматизация с GitHub Actions.
*   **Функционал:**
    *   Регистрация и аутентификация пользователей.
    *   Создание, просмотр, редактирование и удаление профилей котиков.
    *   Загрузка и отображение фотографий котиков.
    *   Работа с API для взаимодействия фронтенда и бэкенда.

## Стек технологий

*   **Frontend:** React
*   **Backend:** Django, Django REST Framework
*   **База данных:** PostgreSQL
*   **Контейнеризация:** Docker, Docker Compose
*   **Сервер фронтенда и прокси:** Nginx
*   **Автоматизация тестирования и доставки (CI/CD):** GitHub Actions
*   **Контейнерный реестр:** Docker Hub

## Установка и запуск

1.  Клонируйте репозиторий:
    ```bash
    git clone https://github.com/Martinez-nbb/kittygram_final.git
    cd kittygram_final
    ```

2.  Убедитесь, что у вас установлены `docker` и `docker-compose`.

3.  Создайте файл `.env` в корне проекта на основе `.env.example` и заполните его актуальными значениями:
    *   `POSTGRES_DB`, `POSTGRES_USER`, `POSTGRES_PASSWORD` — для настройки PostgreSQL.
    *   `SECRET_KEY` — секретный ключ Django (можно сгенерировать с помощью `python -c 'from django.core.management.utils import get_random_secret_key; print(get_random_secret_key())'`).
    *   `DEBUG` — режим отладки (`True` или `False`).
    *   `ALLOWED_HOSTS` — разрешённые хосты для Django.
    *   `DB_HOST` — имя сервиса базы данных в `docker-compose.yml` (обычно `db`).
    *   `DB_PORT` — порт базы данных (обычно `5432`).

4.  Запустите проект с помощью Docker Compose:
    ```bash
    docker-compose up --build
    ```
    Первый запуск может занять некоторое время, так как будут скачаны и собраны все необходимые образы.

5.  Приложение будет доступно по адресу `http://localhost` (если в `docker-compose.yml` указан порт 80) или `http://localhost:<your_mapped_port>`, например, `http://localhost:9000`.

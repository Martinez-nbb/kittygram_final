# Используем образ Python 3.10 (можно обновить на 3.11-slim по желанию)
FROM python:3.10-slim

# Установим рабочую директорию
WORKDIR /app

# Копируем файл зависимостей
COPY requirements.txt .

# Устанавливаем зависимости (включая gunicorn, если он там есть)
RUN pip install --no-cache-dir -r requirements.txt

# Копируем весь проект в контейнер
COPY . .

# Запускаем gunicorn, указывая правильный путь к wsgi-модулю
# Предполагается, что manage.py и kittygram_backend/ находятся в директории /app
CMD ["gunicorn", "--bind", "0.0.0.0:8000", "kittygram_backend.wsgi:application"]

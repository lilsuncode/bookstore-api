# 📚 BookStore API

**BookStore API** — это RESTful бэкенд для онлайн-магазина книг, разработанный на Django Rest Framework. Поддерживает полнотекстовый поиск с помощью Elasticsearch, асинхронные задачи через Celery + RabbitMQ, аутентификацию по OAuth2 и масштабируемую архитектуру.

---

## 🚀 Функционал

- 📖 Управление книгами (CRUD)
- 🔎 Поиск книг по названию, автору, описанию (Elasticsearch)
- 🛒 Добавление в корзину и оформление заказов
- 🔐 Аутентификация через OAuth2 (поддержка Google, GitHub и пр.)
- 📬 Отправка писем и уведомлений через Celery + RabbitMQ
- 📈 Статистика продаж (в разработке)
- 🧪 Покрытие тестами (pytest)

---

## 🛠️ Стек технологий

| Компонент     | Используется                     |
|---------------|----------------------------------|
| Backend       | Django, Django REST Framework    |
| Поиск         | Elasticsearch                    |
| Очереди задач | Celery + RabbitMQ                |
| Аутентификация| OAuth2 (via `django-oauth-toolkit`) |
| БД            | PostgreSQL                       |
| Тестирование  | Pytest, DRF test client          |
| Документация  | Swagger / Redoc (`drf-spectacular`) |

---

## ⚙️ Установка и запуск (локально)

```bash
# Клонируй репозиторий
git clone https://github.com/yourusername/bookstore-api.git
cd bookstore-api

# Активируй виртуальное окружение
python -m venv venv
source venv/bin/activate  # Windows: venv\Scripts\activate

# Установка зависимостей
pip install -r requirements.txt

# Запуск Redis/RabbitMQ/Elasticsearch (с помощью docker-compose)
docker-compose up -d

# Применить миграции и создать суперпользователя
python manage.py migrate
python manage.py createsuperuser

# Запуск Celery воркера
celery -A config worker -l info

# Запуск Django
python manage.py runserver

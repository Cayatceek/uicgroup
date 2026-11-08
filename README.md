# UIC Post

Учебный Django-проект для оформления и отслеживания доставки между филиалами. Включает расчёт стоимости и расстояния, список заказов и просмотр статуса.

## Стек

Python, Django 5.0.4, SQLite, django-crispy-forms, Bootstrap 4 и geopy.

## Локальный запуск

Используйте Python 3.10 или новее, совместимый с зафиксированными зависимостями.

```bash
git clone https://github.com/Cayatceek/uicgroup.git
cd uicgroup
python -m venv .venv
# Активируйте .venv
python -m pip install -r uicpost/requirements.txt
cd uicpost
python manage.py migrate
python manage.py createsuperuser
python manage.py runserver
```

Откройте `http://127.0.0.1:8000/`. Для расчётов и оформления доставки нужны записи филиалов; их можно подготовить через административную панель.

## Структура

- [uicpost/post](uicpost/post/) — модели, формы, представления и шаблоны.
- [map_functions.py](uicpost/post/map_functions.py) — географические расчёты.
- [settings.py](uicpost/uicpost/settings.py) — конфигурация Django.
- [requirements.txt](uicpost/requirements.txt) — зависимости.

## Проверка

Из каталога `uicpost`:

```bash
python manage.py check
python manage.py test
```

## Ограничения

Это учебный прототип, не готовая логистическая система. Расчёты с геокодированием зависят от доступности внешних сервисов. В репозитории присутствует SQLite-база; для собственной работы используйте отдельные тестовые данные. Перед публичным размещением требуется проверить разграничение доступа и заменить настройки разработки.

Лицензия: [LICENSE](LICENSE).

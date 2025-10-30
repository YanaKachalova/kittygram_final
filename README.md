# Kittygram

![Build Status](https://github.com/YanaKachalova/kittygram_final/actions/workflows/main.yml/badge.svg)

Kittygram — это веб-приложение для публикации и просмотра фотографий котов. 
Каждый пользователь может зарегистрироваться, добавить своих питомцев, а также прикрепить их фото и достижения 
Проект реализован на Django REST Framework и предназначен для демонстрации работы API и CI/CD с Docker и GitHub Actions.


## Описание

Kittygram помогает организовать простой и удобный каталог домашних животных. 
Возможности:
- Регистрация и авторизация пользователей;
- Добавление и редактирование карточек котов;
- Загрузка изображений котов;
- Назначение достижений котам;
- Просмотр всех котов и их достижений через.


##  Установка и запуск

### 1. Клонирование репозитория
git clone https://github.com/YanaKachalova/kittygram_final.git
cd kittygram

### 2. Создание и активация виртуального окружения
python -m venv venv
venv\Scripts\activate

### 3. Установление зависимостей
pip install -r requirements.txt

### 4. Выполнение миграций и создание суперпользователя
python manage.py migrate
python manage.py createsuperuser

### 5. Запуск сервера
python manage.py runserver


## Примеры API-запросов

### Получить список котов
GET /api/cats/

Ответ:
[
  {
    "id": 1,
    "name": "Барсик",
    "color": "gray",
    "birth_year": 2020,
    "achievements": [
      {"id": 1, "name": "Самый пушистый"}
    ],
    "owner": "user1"
  }
]

### Добавить кота
POST /api/cats/

Тело запроса:
{
  "name": "Мурзик",
  "color": "white",
  "birth_year": 2023
}

Ответ:
{
  "id": 2,
  "name": "Мурзик",
  "color": "white",
  "birth_year": 2023,
  "owner": "user1"
}

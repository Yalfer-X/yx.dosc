# Документация Yalfer X API
## Описание API
API представляет собой систему управления пользователями в контексте гильдий и участников. Он включает в себя функционал для создания, проверки и обновления данных пользователей, а также управления их профилями, статистикой и экономическими данными.

## Структура проекта
Проект состоит из нескольких модулей, каждый из которых отвечает за определенную функциональность:
- admin;
- donate;
- economy;
- guild;
- mining_pass;
- notifications;
- partners;
- promocodes;
- user.
Каждый модуль подтягивает в себя файлы функциональности, хранящиеся в папках: `service`, `shema`, `database/models`.

## Установка
- Клонирование репозитория:
```
git clone https://github.com/yx.backend.git
cd ваш_репозиторий
```
- Установка зависимостей:
```
cd yx.backend
pip install -r requirements.txt
```
- Настройка базы данных:
  1. Создайте `config.ini` в корне репозитория.
  2. Заполните созданный `config.ini` информацией:
  ```
  [DATABASE]
  host=
  port=
  user=
  password=
  database=
  ```
  3. Настройте соединение с вашей базой данных в файле конфигурации.
- Разверните backend.

## Примеры использования
Основной эндпоинт - это получение/создание аккаунта пользователя:
```
/guild_user
:method: POST
:content-type: application/json
:request body:
{
  "guild_id": integer,
  "member_id": integer,
  "only_get": bool
}
```
```
:reponse-body:
{
  "user": {
    "user": {
      "is_active": true,
      "used_commands": 1,
      "created": "2024-09-08T15:21:52.084715+00:00",
      "is_banned": false,
      "member_id": 0,
      "balance": 0
    },
    "userProfile": {
      "id": 1,
      "first_pin_name": null,
      "member_id": 0,
      "second_pin_name": null,
      "profile_style": "default"
    }
  },
  "guildUser": {
    "id": 1,
    "is_active": true,
    "guild_id": 0,
    "is_banned": false,
    "member_id": 0
  },
  "guild": {
    "is_active": true,
    "guild_id": 0,
    "minings_count": 0,
    "cases": 0,
    "is_banned": false,
    "coins": 0
  },
  "balance": {
    "id": 1,
    "coin": 0,
    "guild_member_id": 1,
    "cases": 0,
    "server_coin": 0
  },
  "mining": {
    "id": 1,
    "buster": null,
    "mining_time": 60,
    "guild_member_id": 1,
    "videocard_lvl": 1
  },
  "miningPass": {
    "id": 1,
    "guild_member_id": 1,
    "is_paid": false,
    "exp": 100,
    "free_taked_lvl": 0,
    "paid_taked_lvl": 0
  },
  "statistic": {
    "id": 1,
    "daily_day": 1,
    "earned_coins": 0,
    "daily": "2024-09-08T15:21:52.125159+00:00",
    "guild_member_id": 1,
    "minings_count": 0,
    "spent_coin": 0,
    "start_daily": "2024-09-08T15:21:52.125159+00:00"
  },
  "partner": {
    "partner_id": null,
    "beginning": null,
    "is_banned": null,
    "is_active": null
  }
}
```

## Вклад
- Если вы хотите внести свой вклад в проект, пожалуйста обращайтесь на наш Discord сервер: https://discord.gg/FcwhkKhFmT.
- Вы можете стать нашим backend-разработчиком по стеку:
```
FastAPI (v0.113.x)
PostgreSQL
Tortoise (0.21.x)
Python (3.10.x)
```
Ждём ваших заявок на Discord сервере: https://discord.gg/FcwhkKhFmT

## Примечание
*Yalfer X и Yalfer X API не являются OpenSource проектами. Доступ к их файлом ограничен*

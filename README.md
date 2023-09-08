# Kittygram

 Социальная сеть для демонстрации ваших домашних питомцев.

## Функциональность
 - Создание профиля
 - Загрузка изображений питомцев
 - Указание достижений питомцев

## Используемые технологии
 - Django
 - Django Rest Framework
 - djoser
 - webcolors
 - Pillow
 - Docker

 ## Ссылка на развернутый сайт
 - https://kittygramm1444.myftp.org/

 ## Установка

 Находясь на удаленном сервере поочередно выполните комманды для установки Docker:
```sh
sudo apt update
sudo apt install curl
curl -fSL https://get.docker.com -o get-docker.sh
sudo sh ./get-docker.sh
sudo apt-get install docker-compose-plugin 
```

Запустите docker-compose в режиме демона:
```sh
sudo docker compose -f docker-compose.production.yml up -d 
```

Выполните миграции и соберите статические файлы:
```sh
sudo docker compose -f docker-compose.production.yml exec backend python manage.py migrate
sudo docker compose -f docker-compose.production.yml exec backend python manage.py collectstatic
sudo docker compose -f docker-compose.production.yml exec backend cp -r /app/collected_static/. /backend_static/static/
```

## Альтернативный вариант проекта
Так же существует версия проекта не упакованная в Docker. Вы можете использовать ее, если вам нужно внести дополнительные изменения в проект.
https://github.com/perineum14/infra_sprint1

## Об авторе 
Егор Пухальский, начинающий Python-разработчик.

[![Build Status](https://github.com/perineum14/kittygram_final/actions/workflows/main.yml/badge.svg?branch=main)]

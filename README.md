[![Main Kittygram workflow](https://github.com/alizunova/kittygram_final/actions/workflows/main.yml/badge.svg)](https://github.com/alizunova/kittygram_final/actions/workflows/main.yml)
# Kittygram: управление котиками
### Учебный проект Яндекс.Практикум курса Python-разработчик(backend)

Kittygram - сервис для любителей котиков.
Можно добавлять фото котиков, их имена, год рождения, цвет и достижения, просматривать чужих котиков.

## *Технологии*

![Django](https://img.shields.io/badge/Django-092E20?logo=django&logoColor=white)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-336791?logo=postgresql&logoColor=white)
![React](https://img.shields.io/badge/React-61DAFB?logo=react&logoColor=black)
![Nginx](https://img.shields.io/badge/Nginx-009639?logo=nginx&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2496ED?logo=docker&logoColor=white)
![GitHub Actions](https://img.shields.io/badge/GitHub_Actions-2088FF?logo=github-actions&logoColor=white)


## *Запуск проекта на удаленном сервере*

1. Установить docker compose на сервер:
```bash
sudo apt update
```
```bash
sudo apt install curl
```
```bash
curl -fSL https://get.docker.com -o get-docker.sh
```
```bash
sudo sh ./get-docker.sh
```
```bash    
sudo apt-get install docker-compose-plugin
```

2. Скачать файл [docker-compose.production.yml](https://github.com/alizunova/kittygram_final/blob/main/docker-compose.production.yml) на свой сервер.

3. На сервере в директории с файлом **docker-compose.production.yml** создать файл  **.env**:
``` bash    
ALLOWED_HOSTS=разрешенные хосты(your.domain.com)
DEBUG=True/False
SECRET_KEY = ключ приложения django
POSTGRES_USER=владелец базы
POSTGRES_PASSWORD=пароль базы
POSTGRES_DB=имя базы
DB_HOST=db
DB_PORT=5432
```        
4. Запустить Docker compose:
``` bash
sudo docker compose -f docker-compose.production.yml up -d
```

5. Собрать статику и применить миграции
``` bash
sudo docker compose -f docker-compose.production.yml exec backend python manage.py migrate
```
``` bash
sudo docker compose -f docker-compose.production.yml exec backend python manage.py collectstatic
```
``` bash
sudo docker compose -f docker-compose.production.yml exec backend cp -r /app/collected_static/. /backend_static/static/
```

## *Автор*
[<span style='color: red;'>**Анна Лизунова**</span>](https://github.com/alizunova)
<span style='color: red;'>long</span>
<style>
blue {
  color: lightblue;
}

red {
  color: red;
}

green {
  color: lightgreen;
}
</style>

A <blue>very</blue> long <red>sentence</red>.

<green>bobbyhadz</green>.com

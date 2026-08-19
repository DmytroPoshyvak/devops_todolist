# INSTRUCTION.md

## Docker Hub

Образ опубліковано в персональному репозиторії Docker Hub:

👉 https://hub.docker.com/r/<your-dockerhub-username>/todoapp

Тег: `1.0.0`

## Збірка образу

```bash
docker build -t todoapp:1.0.0 .
```

## Публікація образу в Docker Hub

```bash
docker login

docker tag todoapp:1.0.0 <your-dockerhub-username>/todoapp:1.0.0

docker push <your-dockerhub-username>/todoapp:1.0.0
```

## Запуск контейнера

Локально зібраний образ:

```bash
docker run -p 8080:8080 todoapp:1.0.0
```

Або образ з Docker Hub:

```bash
docker run -p 8080:8080 <your-dockerhub-username>/todoapp:1.0.0
```

## Доступ до застосунку в браузері

Після запуску контейнера застосунок доступний за адресою:

- Головна сторінка: http://localhost:8080/
- API: http://localhost:8080/api/

Контейнер приймає з'єднання на порту `8080` всередині контейнера, який проброшено на порт `8080` хост-машини через параметр `-p 8080:8080`.
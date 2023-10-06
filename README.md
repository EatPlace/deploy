# Deploy
Создайте файл .env по шаблону .env.example

## Development
```bash
docker-compose up -d
docker compose exec rest_api migrate
```

## Release
В этом режиме собирается готовый образ для production
```bash
docker-compose -f docker-compose.release.yml up -d --build
docker compose exec rest_api migrate
```
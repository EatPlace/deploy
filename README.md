# Deploy

## Development
- Подразумевает, что все нужные репозитории отклонированы в одну папку
- Требуется создать файл `.env` по шаблону `.env.example` 
- Поддерживает изменения на лету, максимально удобен для разработки
```bash
docker-compose up -d
docker compose exec rest_api migrate
```

## Development pulling
- Нужен только репозиторий deploy
- Сборка dev образов с Docker Hub
```bash
docker-compose -f docker-compose.dev.yml up -d
docker compose exec rest_api migrate
```

## Production pulling
- Нужен только репозиторий deploy
- Сборка prod образов с Docker Hub

```bash
docker-compose -f docker-compose.prod.yml up -d
docker compose exec rest_api migrate
```

## Release
- Подразумевает, что все нужные репозитории отклонированы в одну папку
- Требуется создать файл `.prod.env` по шаблону `.env.example`
- В этом режиме собирается готовый compose для production
```bash
docker-compose -f docker-compose.release.yml up -d --build
docker compose exec rest_api migrate
```
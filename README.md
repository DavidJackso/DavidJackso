# Давид Гергиев

**Backend Developer · Go**

С февраля 2023 пишу production-сервисы в Odva Digital Company: ERP-система для управления садом и плодохранилищами (agro-erp.ru), Go-микросервис микромаркетов с интеграцией платёжного терминала и фискализации (vkusnoibistro.com), интеграции для AI-платформы dzyrd.io. Финалист хакатона VK Education × MAX — топ-6 из 2 700 команд.

Интересуют задачи с реальной нагрузкой и нетривиальной архитектурой.

---

## Открытые проекты

### K-TIFY — музыкальный стриминг на микросервисах

→ [github.com/DavidJackso/K-TIFY](https://github.com/DavidJackso/K-TIFY)

Учебный проект, в котором применяю те же подходы, что в production: декомпозиция по доменным зонам, изоляция данных, контрактное взаимодействие через gRPC.

- 4 сервиса (API Gateway, SSO, Tracks, Playlists), каждый со своей PostgreSQL
- gRPC между сервисами + REST наружу через gateway, JWT-аутентификация
- Доменные ошибки пробрасываются через service → gRPC handler и маппятся в точные коды (`NotFound`, `Unauthenticated`, `AlreadyExists`) — не сваливаются в `Internal`
- Correlation ID генерируется gateway и пробрасывается в gRPC-метаданные через interceptor
- Connection pooling настроен явно (`MaxOpenConns`, `MaxIdleConns`, lifetimes)
- Multi-stage Docker билд → distroless образы, healthchecks, миграции отдельным контейнером
- CI на GitHub Actions: golangci-lint + `go test -race` + docker build для каждого сервиса

**Стек:** Go 1.24, gRPC, PostgreSQL 16, Docker, golang-migrate, JWT/bcrypt

### Backend-as-a-Service платформа на Go *(в активной разработке, репозиторий приватный)*

Свой аналог Supabase: поверх PostgreSQL автоматически поднимаются REST API, авторизация и realtime — клиент работает с БД как с готовым backend. Цель — разобрать изнутри, как устроены PostgREST, GoTrue и Realtime.

- **Автогенерация REST API** по `information_schema` PostgreSQL: динамические эндпоинты для таблиц и представлений с фильтрами, пагинацией, сортировкой и выбором полей
- **Row Level Security** через проброс JWT-клеймов в сессионные переменные PostgreSQL — авторизация на уровне БД, а не приложения
- **Realtime-подписки** через PostgreSQL logical replication: чтение WAL → события INSERT/UPDATE/DELETE → рассылка по WebSocket с учётом прав доступа
- Аутентификация: email + bcrypt, выпуск access/refresh JWT, сессии и роли
- Инфраструктура: pgx, миграции, structured logging, graceful shutdown, тесты, запуск через Docker Compose одной командой
  
---

## Стек

**Уверенно:** Go · PostgreSQL · gRPC · REST · Docker · Linux · Git
**Использую:** PHP · MySQL · Nginx · CI/CD · pgx · testify
**Изучаю:** распределённые системы, внутреннее устройство Go (scheduler, GC, escape analysis)

---

## Контакты

- Email — [gutnov3643@gmail.com](mailto:gutnov3643@gmail.com)
- Telegram — [@josephspeedson](https://t.me/josephspeedson)
- LinkedIn — [linkedin.com/in/joseph-joestar-9023b0369](https://www.linkedin.com/in/joseph-joestar-9023b0369/)

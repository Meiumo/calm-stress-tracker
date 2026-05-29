# Спокой — трекер рабочего стресса с ИИ

Спокой помогает фиксировать рабочий стресс, получать поддержку от ИИ в реальном времени и отслеживать динамику самочувствия по неделям.

Пользователь отмечает уровень стресса и рабочие события — приложение отвечает живым советом через DeepSeek, формирует недельную карточку с инсайтами и показывает графики динамики.

---

## Репозитории

| Репо | Описание |
|---|---|
| [self-care-backend](https://github.com/Meiumo/self-care-backend) | REST API на Go: аутентификация, трекинг настроения, стриминговый ИИ, подписки |
| [self-care-mobile](https://github.com/Meiumo/self-care-mobile) | Мобильное приложение на React Native / Expo (iOS, Android) |
| [self-care-deploy](https://github.com/Meiumo/self-care-deploy) | Инфраструктура: Ansible, Docker, Nginx, CI/CD, мониторинг |

---

## Стек

**Backend:** Go, PostgreSQL, JWT, OpenRouter / DeepSeek, Docker, Swagger

**Mobile:** React Native, Expo SDK 54, TypeScript, EAS Build, EAS Update

**Infra:** Ansible, GitHub Actions, Docker Compose, Nginx, Let's Encrypt, Prometheus, Grafana

---

## Архитектура

```
mobile (React Native)
    │
    │  HTTPS / SSE (streaming)
    ▼
backend (Go REST API)
    │
    ├── PostgreSQL
    └── OpenRouter → DeepSeek
```

Деплой — VPS на Ubuntu, Nginx как reverse proxy, SSL через Let's Encrypt. CI/CD: GitHub Actions собирает образ, публикует в GHCR и деплоит через self-hosted runner и Ansible.

---

## Лицензия

MIT


<p align="center">
  <b>Полнофункциональный форум для обсуждений, вопросов и сообществ</b>
</p>

<p align="center">
  <img src="https://img.shields.io/github/license/username/forum?color=blue" alt="License">
  <img src="https://img.shields.io/github/stars/username/forum?style=social" alt="Stars">
  <img src="https://img.shields.io/github/forks/username/forum?style=social" alt="Forks">
  <img src="https://img.shields.io/github/issues/username/forum" alt="Issues">
  <img src="https://img.shields.io/github/last-commit/username/forum" alt="Last commit">
  <img src="https://img.shields.io/badge/PRs-welcome-brightgreen.svg" alt="PRs Welcome">
</p>

<p align="center">
  <a href="#-возможности">Возможности</a> •
  <a href="#-демо">Демо</a> •
  <a href="#-установка">Установка</a> •
  <a href="#-использование">Использование</a> •
  <a href="#-api">API</a> •
  <a href="#-участие">Участие</a>
</p>

---

## 📖 О проекте

**Forum** — это открытый веб-форум с поддержкой тем, ответов, реакций, модерации и уведомлений. Подходит для создания сообществ, Q&A-платформ и внутренних обсуждений в команде.

### Почему Forum?

- ⚡ **Быстрый** — рендеринг на сервере + кэш Redis
- 🔒 **Безопасный** — JWT, CSRF-защита, rate limiting
- 🎨 **Адаптивный** — работает на мобильных и десктопе
- 🧩 **Расширяемый** — плагины, REST API, webhooks
- 🌍 **Мультиязычный** — i18n из коробки

---

## ✨ Возможности

| Модуль | Что умеет |
|--------|-----------|
| 👤 **Пользователи** | Регистрация, вход, профили, аватары, 2FA |
| 📝 **Темы** | Создание, редактирование, категории, теги, черновики |
| 💬 **Сообщения** | Ответы, цитаты, вложения, Markdown, реакции |
| 🛡 **Модерация** | Роли, жалобы, бан, скрытие контента |
| 🔍 **Поиск** | Полнотекстовый по темам и сообщениям |
| 🔔 **Уведомления** | Email, внутренние, web push |
| 📊 **Админка** | Статистика, управление пользователями и настройками |
| 🔌 **API** | REST + Swagger-документация |

---

## 🖼 Демо

![Скриншот форума](docs/screenshot.png)

> 🔗 Живая демка: https://forum.example.com  
> 👤 Тестовый аккаунт: `demo` / `demo1234`

---

## 🛠 Технологии

<p>
  <img src="https://img.shields.io/badge/Node.js-339933?logo=node.js&logoColor=white" alt="Node.js">
  <img src="https://img.shields.io/badge/Express-000000?logo=express&logoColor=white" alt="Express">
  <img src="https://img.shields.io/badge/PostgreSQL-4169E1?logo=postgresql&logoColor=white" alt="PostgreSQL">
  <img src="https://img.shields.io/badge/Redis-DC382D?logo=redis&logoColor=white" alt="Redis">
  <img src="https://img.shields.io/badge/React-61DAFB?logo=react&logoColor=black" alt="React">
  <img src="https://img.shields.io/badge/Docker-2496ED?logo=docker&logoColor=white" alt="Docker">
</p>

- **Backend:** Node.js 20, Express, Prisma
- **Frontend:** React 18, Vite, TailwindCSS
- **БД:** PostgreSQL 16
- **Кэш:** Redis 7
- **Хранилище:** S3 (MinIO / AWS)
- **Тесты:** Jest, Playwright

---

## 📦 Установка

### Требования

- Node.js 20+
- PostgreSQL 16+
- Redis 7+
- Docker (опционально)

### Быстрый старт через Docker

```bash
git clone https://github.com/username/forum.git
cd forum
cp .env.example .env
docker compose up -d
```

Приложение: http://localhost:3000

### Локальная установка

```bash
# 1. Клонировать
git clone https://github.com/username/forum.git
cd forum

# 2. Установить зависимости
npm install

# 3. Настроить окружение
cp .env.example .env
# отредактируйте .env под себя

# 4. Миграции и сиды
npm run migrate
npm run seed

# 5. Запуск (dev)
npm run dev
```

---

## ⚙️ Конфигурация

Пример `.env`:

```env
# App
NODE_ENV=development
PORT=3000
APP_URL=http://localhost:3000

# Database
DATABASE_URL=postgresql://user:pass@localhost:5432/forum

# Redis
REDIS_URL=redis://localhost:6379

# Auth
JWT_SECRET=change-me
JWT_EXPIRES_IN=7d

# Email
SMTP_HOST=smtp.example.com
SMTP_PORT=587
SMTP_USER=user@example.com
SMTP_PASS=secret

# Storage
S3_ENDPOINT=http://localhost:9000
S3_BUCKET=forum-uploads
S3_ACCESS_KEY=minio
S3_SECRET_KEY=minio123
```

---

## 🚀 Использование

### Создать тему

1. Войдите или зарегистрируйтесь
2. Нажмите **«Новая тема»**
3. Выберите категорию, заполните заголовок и текст
4. Нажмите **«Опубликовать»**

### Роли и права

| Роль | Просмотр | Создание | Модерация | Админка |
|------|:--------:|:--------:|:---------:|:-------:|
| Гость | ✅ | ❌ | ❌ | ❌ |
| Пользователь | ✅ | ✅ | ❌ | ❌ |
| Модератор | ✅ | ✅ | ✅ | ❌ |
| Админ | ✅ | ✅ | ✅ | ✅ |

### Скрипты

```bash
npm run dev        # запуск в dev-режиме
npm run build      # сборка
npm start          # production
npm test           # юнит-тесты
npm run test:e2e   # e2e-тесты
npm run lint       # линтер
npm run migrate    # миграции
npm run seed       # наполнение тестовыми данными
```

---

## 🔌 API

Базовый URL: `http://localhost:3000/api`

```http
GET     /api/topics                # список тем
POST    /api/topics                # создать тему
GET     /api/topics/:id            # тема с ответами
PATCH   /api/topics/:id            # изменить тему
DELETE  /api/topics/:id            # удалить тему
POST    /api/topics/:id/replies    # добавить ответ
POST    /api/auth/register         # регистрация
POST    /api/auth/login            # вход
GET     /api/users/me              # текущий пользователь
```

**Пример запроса:**

```bash
curl -X POST http://localhost:3000/api/topics \
  -H "Authorization: Bearer <token>" \
  -H "Content-Type: application/json" \
  -d '{"title":"Привет","body":"Первая тема","categoryId":1}'
```

📚 Полная документация: http://localhost:3000/api/docs (Swagger UI)

---

## 🐳 Docker

```bash
# Собрать образ
docker build -t forum:latest .

# Запустить
docker run -p 3000:3000 --env-file .env forum:latest

# Или через compose
docker compose up -d
docker compose logs -f
```

---

## 🧪 Тестирование

```bash
npm test                    # все юнит-тесты
npm test -- --coverage      # с покрытием
npm run test:e2e            # Playwright
npm run lint                # ESLint + Prettier
```

CI настроен через GitHub Actions — см. [`.github/workflows/ci.yml`](.github/workflows/ci.yml).

---

## 🗺 Roadmap

- [x] Базовые темы и ответы
- [x] Авторизация и роли
- [x] Поиск
- [ ] Реакции и упоминания
- [ ] Web push-уведомления
- [ ] Мобильное приложение
- [ ] Плагины и маркетплейс тем

Актуальный план: [Projects](https://github.com/username/forum/projects)

---

## 🤝 Участие

Мы рады любому вкладу!

```bash
# 1. Форк
# 2. Ветка
git checkout -b feature/amazing-feature

# 3. Коммит
git commit -m "feat: add amazing feature"

# 4. Пуш
git push origin feature/amazing-feature

# 5. Pull Request
```

Пожалуйста, ознакомьтесь с [CONTRIBUTING.md](CONTRIBUTING.md) и [CODE_OF_CONDUCT.md](CODE_OF_CONDUCT.md).

Используем [Conventional Commits](https://www.conventionalcommits.org/):
`feat:`, `fix:`, `docs:`, `chore:`, `refactor:`.

---

## 🐛 Баги и предложения

- Нашли баг? → [Issues](https://github.com/username/forum/issues/new?template=bug_report.md)
- Есть идея? → [Feature request](https://github.com/username/forum/issues/new?template=feature_request.md)
- Вопрос? → [Discussions](https://github.com/username/forum/discussions)

---

## 📄 Лицензия

Проект распространяется под лицензией **MIT** — см. [LICENSE](LICENSE).

---

## 👥 Авторы

- **Ваше Имя** — [@username](https://github.com/username)

См. полный список [участников](https://github.com/username/forum/graphs/contributors).

---

## ⭐ Поддержите проект

Если форум оказался полезен — поставьте звезду ⭐ и поделитесь с друзьями!

<p align="center">
  <a href="https://github.com/username/forum/stargazers">
    <img src="https://img.shields.io/github/stars/username/forum?style=for-the-badge" alt="Stars">
  </a>
</p>

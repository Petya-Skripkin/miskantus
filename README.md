# Residence des Muses – Clone Frontend

Vue 3 проект с полным контентом сайта [residence-des-muses.ch](https://residence-des-muses.ch/).

## Запуск

```bash
npm install
npm run dev
```

Откройте http://localhost:5173

## Сборка

```bash
npm run build
npm run preview
```

## Страницы

| Страница | Путь | Контент |
|----------|------|---------|
| Projet | `/projet` | Описание проекта, 10 вилл, материалы |
| Situation | `/situation` | Coffrane, тексты, галерея, карта |
| Les villas | `/les-villas` | Планировка, энергия, бюджеты, экстерьеры |
| Galerie | `/galerie` | Галерея с лайтбоксом |
| Plans & Prix | `/plans` | Таблица вилл, статусы, PDF |
| Téléchargements | `/telechargements` | Брошюра, планы |
| Contact | `/contact` | Форма, Marco Romano, партнёры |

## Мобильная версия

- Адаптивная верстка (mobile-first)
- Бургер-меню на экранах < 768px
- Карточки вместо таблицы на Plans
- Карусель с touch-friendly кнопками (44px)

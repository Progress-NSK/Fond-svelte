![Svelte Logo](https://st.timeweb.com/cloud-static/apps-logo/svelte.svg)

# Svelte Starter (готов к запуску)

Подготовленный репозиторий для старта Svelte-приложения на Rollup.

## Запуск локально

```bash
npm install
npm run dev
```

После запуска приложение доступно на `http://localhost:5000`.

## Сборка production

```bash
npm run build
npm run start
```

`npm run build` собирает файлы в `public/build`,
`npm run start` поднимает локальный сервер для проверки статики.

## Структура

- `src/` — исходники приложения (Svelte-компоненты и точка входа)
- `public/` — статические файлы и готовый build
- `rollup.config.js` — конфигурация сборки

## Что уже готово

- Базовая структура проекта и точка входа.
- Скрипты для разработки, сборки и локального предпросмотра.
- Стартовый UI-экран с подсказками по следующим шагам.
